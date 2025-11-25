# Optimizing Signaling Strategies in Online Teaching: A Data-Driven Approach

Effective signaling in instructional materials—through cues such as
highlights, arrows, and annotations—can guide learner attention, reduce
cognitive load, and enhance comprehension in multimedia-rich online
courses. While the benefits of signaling are well documented, little is
known about how combinations of signaling strategies influence both the
average performance and the consistency of student outcomes. In this
study, we propose a data-driven approach to evaluate and optimize
signaling strategies in online teaching. Using lecture materials from
three semesters of introductory and intermediate statistics courses, we
extracted multiple features of textual and visual signaling, including
highlighted words, annotated formulas, arrows, and notes. Principal
Component Analysis identified four distinct signaling strategies
employed by the instructor. We then applied a heteroscedastic beta
regression model to link these strategies to topic-level exam
performance, allowing simultaneous assessment of mean learning outcomes
and variability across students. Results show that strategies combining
formula highlighting with arrows and detailed notes improve both the
average proportion of successful learners and the stability of outcomes,
while relying solely on formula highlighting increases variability. Our
findings provide actionable guidance for instructors to design effective
signaling strategies, and demonstrate a flexible framework for
data-driven evaluation of teaching practices in online learning
environments.

# Data Preprocessing and Extracting Singaling Strategies

-   downloading the data

-   scaling the data

-   downloading the responses

-   extracting the signaling strategies

-   plotting the PC loadings

<img src="README_files/figure-markdown_strict/figstrat1-1.png" alt="Bar plots showing the feature weights for the four signaling strategies extracted by PCA. The labels correspond to the underlying observed variables, while the term “extra” indicates weights associated with the squared versions of these variables." width="100%"  />
<p class="caption">
Bar plots showing the feature weights for the four signaling strategies
extracted by PCA. The labels correspond to the underlying observed
variables, while the term “extra” indicates weights associated with the
squared versions of these variables.
</p>

# Beta Regression with Heteroscedasticity

-   regression results

<table>
<caption>Heteroscedastic Beta Regression Results for Mean and Precision
Components.</caption>
<thead>
<tr class="header">
<th style="text-align: left;">component</th>
<th style="text-align: left;">term</th>
<th style="text-align: left;">estimate</th>
<th style="text-align: left;">std.error</th>
<th style="text-align: left;">statistic</th>
<th style="text-align: left;">p.value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;">mean</td>
<td style="text-align: left;">(Intercept)</td>
<td style="text-align: left;">0.3923</td>
<td style="text-align: left;">0.0765</td>
<td style="text-align: left;">5.1260</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="even">
<td style="text-align: left;">mean</td>
<td style="text-align: left;">complex</td>
<td style="text-align: left;">-0.4484</td>
<td style="text-align: left;">0.0956</td>
<td style="text-align: left;">-4.6888</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="odd">
<td style="text-align: left;">mean</td>
<td style="text-align: left;">S1</td>
<td style="text-align: left;">0.0684</td>
<td style="text-align: left;">0.0129</td>
<td style="text-align: left;">5.3168</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="even">
<td style="text-align: left;">mean</td>
<td style="text-align: left;">S2</td>
<td style="text-align: left;">0.1010</td>
<td style="text-align: left;">0.0313</td>
<td style="text-align: left;">3.2307</td>
<td style="text-align: left;">0.0012</td>
</tr>
<tr class="odd">
<td style="text-align: left;">mean</td>
<td style="text-align: left;">S3</td>
<td style="text-align: left;">0.0420</td>
<td style="text-align: left;">0.0184</td>
<td style="text-align: left;">2.2832</td>
<td style="text-align: left;">0.0224</td>
</tr>
<tr class="even">
<td style="text-align: left;">mean</td>
<td style="text-align: left;">S4</td>
<td style="text-align: left;">0.1519</td>
<td style="text-align: left;">0.0322</td>
<td style="text-align: left;">4.7205</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="odd">
<td style="text-align: left;">precision</td>
<td style="text-align: left;">(Intercept)</td>
<td style="text-align: left;">2.4455</td>
<td style="text-align: left;">0.2597</td>
<td style="text-align: left;">9.4177</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="even">
<td style="text-align: left;">precision</td>
<td style="text-align: left;">complex</td>
<td style="text-align: left;">-0.1698</td>
<td style="text-align: left;">0.4061</td>
<td style="text-align: left;">-0.4180</td>
<td style="text-align: left;">0.6759</td>
</tr>
<tr class="odd">
<td style="text-align: left;">precision</td>
<td style="text-align: left;">S1</td>
<td style="text-align: left;">0.4505</td>
<td style="text-align: left;">0.1032</td>
<td style="text-align: left;">4.3667</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="even">
<td style="text-align: left;">precision</td>
<td style="text-align: left;">S2</td>
<td style="text-align: left;">-0.2841</td>
<td style="text-align: left;">0.1246</td>
<td style="text-align: left;">-2.2805</td>
<td style="text-align: left;">0.0226</td>
</tr>
<tr class="odd">
<td style="text-align: left;">precision</td>
<td style="text-align: left;">S3</td>
<td style="text-align: left;">0.4485</td>
<td style="text-align: left;">0.1531</td>
<td style="text-align: left;">2.9288</td>
<td style="text-align: left;">0.0034</td>
</tr>
<tr class="even">
<td style="text-align: left;">precision</td>
<td style="text-align: left;">S4</td>
<td style="text-align: left;">0.0972</td>
<td style="text-align: left;">0.1856</td>
<td style="text-align: left;">0.5238</td>
<td style="text-align: left;">0.6004</td>
</tr>
</tbody>
</table>

Heteroscedastic Beta Regression Results for Mean and Precision
Components.

-   summaries for the parameters

<table>
<caption>Summaries of the estimated means and standard deviations of the
resulting beta distributions.</caption>
<colgroup>
<col style="width: 9%" />
<col style="width: 12%" />
<col style="width: 22%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 22%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th style="text-align: left;"></th>
<th style="text-align: left;">minimum</th>
<th style="text-align: left;">lower quartile</th>
<th style="text-align: left;">median</th>
<th style="text-align: left;">mean</th>
<th style="text-align: left;">upper quartile</th>
<th style="text-align: left;">maximum</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;">means</td>
<td style="text-align: left;">0.3539</td>
<td style="text-align: left;">0.4987</td>
<td style="text-align: left;">0.5714</td>
<td style="text-align: left;">0.5769</td>
<td style="text-align: left;">0.6482</td>
<td style="text-align: left;">0.8149</td>
</tr>
<tr class="even">
<td style="text-align: left;">sds</td>
<td style="text-align: left;">0.0105</td>
<td style="text-align: left;">0.1324</td>
<td style="text-align: left;">0.1695</td>
<td style="text-align: left;">0.1530</td>
<td style="text-align: left;">0.1912</td>
<td style="text-align: left;">0.2101</td>
</tr>
</tbody>
</table>

Summaries of the estimated means and standard deviations of the
resulting beta distributions.

-   selected shapes

<img src="README_files/figure-markdown_strict/figshapes-1.png" alt="Fitted beta distribution densities for a selection of teaching cases, illustrating variation in mean and scale parameters across the modelled topics." width="100%"  />
<p class="caption">
Fitted beta distribution densities for a selection of teaching cases,
illustrating variation in mean and scale parameters across the modelled
topics.
</p>

-   the estimated mean parameters versus the strategy scores

<table>
<caption>Average strategy scores for the four signaling strategies
across different ranges of the fitted mean parameter <span
class="math inline"><em>μ</em></span> indicating how strategy usage
relates to topic-level performance.</caption>
<thead>
<tr class="header">
<th style="text-align: left;">mean <span
class="math inline"><em>μ̂</em></span></th>
<th style="text-align: left;">S1</th>
<th style="text-align: left;">S2</th>
<th style="text-align: left;">S3</th>
<th style="text-align: left;">S4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;">small</td>
<td style="text-align: left;">-0.4772</td>
<td style="text-align: left;">-0.5781</td>
<td style="text-align: left;">-0.0749</td>
<td style="text-align: left;">-0.3636</td>
</tr>
<tr class="even">
<td style="text-align: left;">medium</td>
<td style="text-align: left;">-0.7630</td>
<td style="text-align: left;">0.2854</td>
<td style="text-align: left;">-0.2250</td>
<td style="text-align: left;">0.7279</td>
</tr>
<tr class="odd">
<td style="text-align: left;">large</td>
<td style="text-align: left;">1.6194</td>
<td style="text-align: left;">1.7084</td>
<td style="text-align: left;">0.0037</td>
<td style="text-align: left;">0.0816</td>
</tr>
</tbody>
</table>

Average strategy scores for the four signaling strategies across
different ranges of the fitted mean parameter *μ* indicating how
strategy usage relates to topic-level performance.

-   the estimated precision parameters versus the strategy scores

<table>
<caption>Average strategy scores for the four signaling strategies
across different ranges of the fitted precision parameter <span
class="math inline"><em>ϕ</em></span> indicating how strategy usage
relates to topic-level performance.</caption>
<thead>
<tr class="header">
<th style="text-align: left;">precision <span
class="math inline"><em>ϕ̂</em></span></th>
<th style="text-align: left;">S1</th>
<th style="text-align: left;">S2</th>
<th style="text-align: left;">S3</th>
<th style="text-align: left;">S4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;">small</td>
<td style="text-align: left;">-0.6532</td>
<td style="text-align: left;">0.4038</td>
<td style="text-align: left;">-0.3813</td>
<td style="text-align: left;">0.1163</td>
</tr>
<tr class="even">
<td style="text-align: left;">medium</td>
<td style="text-align: left;">0.9395</td>
<td style="text-align: left;">-0.7317</td>
<td style="text-align: left;">0.4427</td>
<td style="text-align: left;">-0.4473</td>
</tr>
<tr class="odd">
<td style="text-align: left;">large</td>
<td style="text-align: left;">4.0539</td>
<td style="text-align: left;">-2.0026</td>
<td style="text-align: left;">2.7190</td>
<td style="text-align: left;">0.2114</td>
</tr>
</tbody>
</table>

Average strategy scores for the four signaling strategies across
different ranges of the fitted precision parameter *ϕ* indicating how
strategy usage relates to topic-level performance.

Overall, this study highlights the value of combining detailed
instructional feature extraction with robust statistical modeling to
inform evidence-based improvements in teaching and learning. By focusing
on both the magnitude and consistency of learning outcomes, instructors
can design signaling strategies that maximize comprehension and ensure
more equitable success across students.
