Download Link: https://assignmentchef.com/product/solved-stats506-problem-set-4
<br>
<h1>Question 1</h1>

<a href="https://jbhender.github.io/Stats506/F18/Intro_to_SQL.html">Use the Lahman baseball data previously seen in the SQL notes</a>

<a href="https://jbhender.github.io/Stats506/F18/Intro_to_SQL.html">(https://jbhender.github.io/Stats506/F18/Intro_to_SQL.html) to an</a>swer this question. Your answer should be a single SQL query, but may require anonymous tables created using nested queries.

Write an SQL query to construct a table showing the <em>all-time</em> leader in <em>hits</em> (“H” from the “batting” table) for each birth country (“birthCountry” in the “master” table). An <em>all-time</em> leader is the player (“playerID”) with the most total hits across all rows (e.g. seasons/stints). Limit your table to players/countries with at least 200 hits and order the table by descending number of hits. Create a nicely formatted table with the following columns as your final output: Player (nameFirst nameLast), Debut (debut), Country of Birth (birthCountry), Hits (H).

<h1>Question 2</h1>

In this question you will modify your answer to Problem Set 3, Question 2 (PS3 Q2) to practice parallel, asynchronous, and batch computing. Copy the functions from part a and c of PS3 Q2 to a new file ps4_q2_funcs.R

In each of the parts below, let <em>β</em>∈ℝ<sup>100</sup> be defined so that

,

<em>i              </em>0

and Σ be block diagonal with Σ<em><sub>i</sub></em><em>j </em>= <em>ρβ<sub>i</sub>β<sub>j</sub></em> when <em>i </em>≠ <em>j</em> and Σ<em><sub>i</sub></em><em>i </em>= 1. (You may also use <em>β</em> as in PS3 Q2 and rescale in any other way that results in a positive definite Σ.) Create a table or plot for your results from each part.

<ol start="3">

 <li>Write an R script R that sources ps4_q2_funcs.R , and then uses mclapply to run parallel simulations for <em>ρ</em>∈ {.25<em>i</em>}3<em><sub>i</sub></em><sub>=−3</sub>.</li>

</ol>

Let <em>σ </em>= 1 and use 10,000 Monte Carlo replications. Reorganize the results into a long data frame results_q4a with columns: “rho”, “sigma”, “metric”, “method”, “est”, and “se”. “Metric” should

contain the assessment measure: FWER, FDR, Sensitivity, or Specificity and “method” the multiple comparison method used. The columns “est” and “se” should contain the Monte Carlo estimate and its standard error, respectively.

<ol>

 <li>Use your script from part a as the basis for a new script R . Setup a 4 core cluster using doParallel and then use nested foreach loops to run simulations for <em>ρ</em>∈ {.25<em>i</em>}3<em><sub>i</sub></em><sub>=−3</sub> and</li>

</ol>

<em>σ </em>= {.25, .5, 1}. Reshape the results as before into results_q4b saved to a file

results_q4b.RData . Use a PBS file to run this script on the Flux cluster.

<ol>

 <li>Modify your script from part a to create R which reads the following arguments from the command line: sigma , mc_rep , and n_cores . Also modify the script to use the futures package for parallelism. Use a PBS file to run this script as a job array for <em>σ </em>= {.25, .5, 1}. <em>Hint: see the answer </em><a href="https://stackoverflow.com/questions/12722095/how-do-i-use-floating-point-division-in-bash"><em>at this page (https://stackoverflow.com/questions/12722095/how-do-i-use-floating-point-division-inbash) for how to convert </em></a><a href="https://stackoverflow.com/questions/12722095/how-do-i-use-floating-point-division-in-bash"><em>$PBS_ARRAYID</em></a><a href="https://stackoverflow.com/questions/12722095/how-do-i-use-floating-point-division-in-bash"><em> to </em></a><a href="https://stackoverflow.com/questions/12722095/how-do-i-use-floating-point-division-in-bash"><em>sigma</em></a> <a href="https://stackoverflow.com/questions/12722095/how-do-i-use-floating-point-division-in-bash"><em>.</em></a></li>

</ol>

<h1>Question 3</h1>

<a href="https://www.cms.gov/Research-Statistics-Data-and-Systems/Statistics-Trends-and-Reports/Medicare-Provider-Charge-Data/Physician-and-Other-Supplier.html">For this question you should use the 2016 Medicare Provider Utilization and Payment data available here here (https://www.cms.gov/Research-Statistics-Data-and-Systems/Statistics-Trends-and-Reports/MedicareProvider-Charge-Data/Physician-and-Other-Supplier.html)</a><a href="https://www.cms.gov/Research-Statistics-Data-and-Systems/Statistics-Trends-and-Reports/Medicare-Provider-Charge-Data/Physician-and-Other-Supplier.html">.</a>

<ol>

 <li>Put the data into a folder ./data and then follow the instructions to read this data into SAS.</li>

 <li>Use one or more data steps to reduce the data set to those rows with “MRI” in the ‘hcpcs_description’ field and where ‘hcpcs_code’ starts with a 7.</li>

 <li>Use proc means or proc summary (as needed) to determine the MRI procedures with the highest volume, highest total payment, and highest average payment among the procedures represented here. d. Repeat part b-c using PROC SQL.</li>

 <li>Export the results from “c” and “d” to csv and verify that they match. You do <em>not</em> need to produce a nice table within your solution document.</li>

</ol>