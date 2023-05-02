Download Link: https://assignmentchef.com/product/solved-cpe211-project-6
<br>



<strong> </strong>




<h2>&lt;Project 6 Description&gt;</h2>




You will write a program that performs the following tasks (read and understand number 6 and 7):




<ul>

 <li>Command line arguments are to be used to open the input file and the output file. The first attempt for the open is using the file names provided as command line arguments.  The first argument is the input file and the second is the output file.  The program is to test for the correct number of arguments. <strong> If an incorrect number of arguments is used, output a message and terminate the program </strong>– run the sample solution to see what the message is.</li>

 <li>Open a user-specified file for input. If the input file name provided as a command line argument fails to open successfully, enter into a loop that prints out an error message, resets the input file stream variable <strong>(see the hints section #1),</strong> obtains a new file name, echo prints the filename and tries to open the new file.  The loop continues until the user successfully enters a valid file name or presses ctrl-c to exit.  The first file name tried will come from the command line <strong>(hints #12)</strong></li>

</ul>




<ul>

 <li>Open a user-specified file for output. .  If the output file name provided as a command line argument fails to open successfully, enter into a loop that prints out an error message, resets the output file stream variable <strong>(see the hints section #1),</strong> obtains a new file name, echo prints the filename and tries to open the new file.  The loop continues until the user successfully enters a valid file name or presses ctrl-c to exit.   The first file name tried will come from the command line <strong>(hints #12)</strong></li>

 <li>If the input file is empty, your program shall <strong><u>write a message to the terminal AND the output file</u></strong> indicating that the input file was empty. Note if the input file is empty, an empty input file message only is written to the output file (no header information). <strong>(see the hints section #2)</strong></li>

</ul>




<ul>

 <li>All other output is to be written to the output file</li>

 <li>The input file contains <strong>integer assignment scores</strong> for several students (one student and scores per line). For each student in the file, the program reads a student’s last name, first name, their quiz grades, their homework grades and their exam scores.  Score values are in the range 0 to 100 inclusive.  Look at all of the provided input files to see what the information looks like.</li>

</ul>







<ul>

 <li>Column header information and the key values are written to the output file as shown by running the sample solution. All column values are placed in a specific field width as specified in hints section #10.</li>

 <li>As shown in the sample solution, print a summary of each student’s information:

  <ol>

   <li>The number associated with the student (from their order in the input file)</li>

   <li>Up to 10 characters (use substring function) of the last name,</li>

   <li>Up to 5 characters (use substring function) of the first name,</li>

   <li>The total of the quiz scores,</li>

   <li>The total of the homework scores,</li>

   <li>The total of the exam scores, and</li>

   <li>The students average (sum of their scores divided by the sum of the key values)</li>

  </ol></li>

</ul>

<strong>Print out the average as a percent with a precision of 2 decimal places (i.e. 67.87). </strong>




<ul>

 <li>If one or more students are in the class, compute and output the class average after the information for all students has been read and output, Compute and output the class average.  If no student        information is in the file output a message to the output file and the terminal (as shown in the sample        solution)</li>

</ul>




Possible valid assignment scores are <strong>integers</strong> in the range from 0 to 100, inclusive.  If an input file is not empty, you may assume that any data that appears within that file is valid data.  Valid files will have at least the key line.  No score will exceed 100 points.




Remember the first line of input in the file contains the number of assignments for each category and the second line contains the key values.  These are used to determine the maximum score possible for a student, and this maximum score is what is used to determine a student’s average.  The algorithm provided in the slides indicates one method that the line of key values can be processed differently from the student information.




<strong>All scores are integer values, so use integer variables to hold the values read and the sum of the values.</strong>  Use floating point variables to hold all averaged values (watch out for integer division).  <strong>Note: setprecision and fixed affect the number of decimal places shown for floating point values and not integer values. </strong>

<strong> </strong>

<h2>&lt;Project 6 C++ Hints&gt;</h2>




<ol>

 <li>Resetting the input stream variable: In Dev C++ and g++, the clear function must be used on a file stream that is repeatedly reopened in a loop. Some compilers do not require this clearing.  Therefore, to allow for more portability of the code, use the following statement in your while loop that executes until a valid filename is entered:</li>

</ol>




<strong>Input_file_stream_var.clear(); </strong>

Where <strong>Input_file_stream_var</strong> is the name of your input file stream variable




<ol start="2">

 <li>Testing for an empty input file is performed by tyring to read the number of quiz, homework and exam scores, and then testing the status of the file stream after the read. If the file stream is in the fail state and the end of file status is true, print out an the empty file message and terminate the program. If the file stream is valid after the priming read, , print out the headings and then perform a priming read of a student’s last name  – before the while loop is entered.  If the file stream is valid after this read, proceed to the loop to process and read the rest of the input file</li>

</ol>




<ol start="3">

 <li>If the priming read of the last name results in the input stream entering the fail state, print out a message to the <strong>terminal and the output file </strong>stating that no student information is in the file.</li>

</ol>




<ol start="4">

 <li>Use an end-of-file while loop to read and process all information in the input file – this will be an outer loop. Priming read for this loop is the last name of the student</li>

</ol>




<ol start="5">

 <li>Use three count controlled loops for reading in the assignment scores for the three categories: quiz scores, homework scores and exam scores.</li>

</ol>




<ol start="6">

 <li>All assignment scores will be integer values. Scores used will be valid values in the range of 0 to 100.  A negative score indicates that the assignment was not submitted (score counted as a 0) – this value is not added to the total score for the category (quiz, homework or exam) in which it belongs.</li>

</ol>




<ol start="7">

 <li>Integer variables to hold the points a student earned for each category (quizzes, homework and exam) are needed. A floating point variable for holding the average test score for a student is also needed.</li>

</ol>




<ol start="8">

 <li>A floating point variable to hold the sum of the averages for all students is required. An integer variable to hold the number of students in the class is required.</li>

</ol>




<ol start="9">

 <li>Summing the averages for each student and then dividing that sum by the number of students in the class determines the class average.</li>

</ol>




<ol start="10">

 <li><strong>Procedure for processing a file:</strong> read in the information for a single student, process it, output the necessary information and then read in information for the next student. Use a loop</li>

</ol>




<ol start="11">

 <li>The following line of code creates the dashes under the column headings. It also provides the setw field values for the columns.  <strong>All output is left justified in the fields specified</strong>.</li>

</ol>




<strong>coutFile &lt;&lt; setw(3) &lt;&lt; “-” &lt;&lt; setw(12) &lt;&lt; “———-” &lt;&lt; setw(7) &lt;&lt; “—–” </strong>

<strong>         &lt;&lt; setw(6) &lt;&lt; “—-” &lt;&lt; setw(6) &lt;&lt; “—” &lt;&lt; setw(6) &lt;&lt; “—-”           &lt;&lt; setw(7) &lt;&lt; “—–” &lt;&lt; setw(9) &lt;&lt; “——-” &lt;&lt; endl;</strong>







<ol start="12">

 <li>Run the sample solution to see what is contained in the output file – column headings, information output and general format of what the output is supposed to look like.</li>

</ol>




<ol start="13">

 <li>In this assignment the first attempt at input and output filenames will come from the command line when the program is run</li>

</ol>

<h3>./Project_06  InputFileName  OutputFileName</h3>

If these files fail to open then a loop is entered as described in the project description steps 1 and 2 on page 2




<h2>&lt;Project 6 Command Line Arguments&gt;</h2>




In this project the initial input and output file names are provided to the program via command line arguments.  The program is to initially try to open the filenames provided for input and output.  If the open fails for a file, then a loop is entered to prompt the user for the name of the input or output file until the file is successfully opened.




The command typed at the terminal prompt is as shown below and in the hints section:




<h3>./Project_06  InputFileName  OutputFileName</h3>




For the program to be able to use the command line arguments, code must be added to the program to read the arguments.

First, change the main function heading as shown below:

Change:   <strong>int main() to int main(int argc, char* argv[]) </strong>

The variable argc contains the number of command line arguments.  This count includes the executable file name.  The variable argv[ ] is a character array holding the command line arguments as c-string values.  For the following run of a program




<strong>./Project_06  P6_in1.txt  Out1.txt </strong>




argc has a value of 3 and the character array has values of argv[0] = ./Project_06, argv[1] = P6_in1.txt and argv[2] = Out1.txt.  To use the file names in the program, they can be assigned to a string variable or used directly in the open function.  Below, the input file name is assigned to a string variable and the string variable is used in the open function.  For the output file, the specified output file is used directly in the open function.




<strong>string inputFileName; </strong>

<strong>inputFileName = argv[1]; // assign command line argument value to a string variable</strong><strong> inFile.open(inputFileName.c_str()); </strong>

<strong> </strong>

<strong>outFile.open(argv[2]);  // use command line argument directly in the open function</strong>


