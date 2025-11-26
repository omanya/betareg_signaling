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
<td style="text-align: left;">0.3098</td>
<td style="text-align: left;">0.0572</td>
<td style="text-align: left;">5.4154</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="even">
<td style="text-align: left;">mean</td>
<td style="text-align: left;">complex</td>
<td style="text-align: left;">-0.3590</td>
<td style="text-align: left;">0.0478</td>
<td style="text-align: left;">-7.5096</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="odd">
<td style="text-align: left;">mean</td>
<td style="text-align: left;">S1</td>
<td style="text-align: left;">0.0842</td>
<td style="text-align: left;">0.0096</td>
<td style="text-align: left;">8.7786</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="even">
<td style="text-align: left;">mean</td>
<td style="text-align: left;">S2</td>
<td style="text-align: left;">0.0686</td>
<td style="text-align: left;">0.0279</td>
<td style="text-align: left;">2.4609</td>
<td style="text-align: left;">0.0139</td>
</tr>
<tr class="odd">
<td style="text-align: left;">mean</td>
<td style="text-align: left;">S3</td>
<td style="text-align: left;">0.0280</td>
<td style="text-align: left;">0.0089</td>
<td style="text-align: left;">3.1419</td>
<td style="text-align: left;">0.0017</td>
</tr>
<tr class="even">
<td style="text-align: left;">mean</td>
<td style="text-align: left;">S4</td>
<td style="text-align: left;">0.0663</td>
<td style="text-align: left;">0.0265</td>
<td style="text-align: left;">2.4977</td>
<td style="text-align: left;">0.0125</td>
</tr>
<tr class="odd">
<td style="text-align: left;">precision</td>
<td style="text-align: left;">(Intercept)</td>
<td style="text-align: left;">3.0447</td>
<td style="text-align: left;">0.2611</td>
<td style="text-align: left;">11.6628</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="even">
<td style="text-align: left;">precision</td>
<td style="text-align: left;">complex</td>
<td style="text-align: left;">0.1335</td>
<td style="text-align: left;">0.4132</td>
<td style="text-align: left;">0.3231</td>
<td style="text-align: left;">0.7466</td>
</tr>
<tr class="odd">
<td style="text-align: left;">precision</td>
<td style="text-align: left;">S1</td>
<td style="text-align: left;">0.5955</td>
<td style="text-align: left;">0.1029</td>
<td style="text-align: left;">5.7869</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="even">
<td style="text-align: left;">precision</td>
<td style="text-align: left;">S2</td>
<td style="text-align: left;">-0.7990</td>
<td style="text-align: left;">0.1222</td>
<td style="text-align: left;">-6.5389</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="odd">
<td style="text-align: left;">precision</td>
<td style="text-align: left;">S3</td>
<td style="text-align: left;">0.9208</td>
<td style="text-align: left;">0.1541</td>
<td style="text-align: left;">5.9742</td>
<td style="text-align: left;">0.0000</td>
</tr>
<tr class="even">
<td style="text-align: left;">precision</td>
<td style="text-align: left;">S4</td>
<td style="text-align: left;">0.4426</td>
<td style="text-align: left;">0.1865</td>
<td style="text-align: left;">2.3733</td>
<td style="text-align: left;">0.0176</td>
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
<td style="text-align: left;">0.4025</td>
<td style="text-align: left;">0.4864</td>
<td style="text-align: left;">0.5578</td>
<td style="text-align: left;">0.5608</td>
<td style="text-align: left;">0.5907</td>
<td style="text-align: left;">0.8238</td>
</tr>
<tr class="even">
<td style="text-align: left;">sds</td>
<td style="text-align: left;">0.0006</td>
<td style="text-align: left;">0.0871</td>
<td style="text-align: left;">0.1502</td>
<td style="text-align: left;">0.1308</td>
<td style="text-align: left;">0.1785</td>
<td style="text-align: left;">0.2010</td>
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
<td style="text-align: left;">-0.5328</td>
<td style="text-align: left;">-0.4102</td>
<td style="text-align: left;">-0.1041</td>
<td style="text-align: left;">-0.1513</td>
</tr>
<tr class="even">
<td style="text-align: left;">medium</td>
<td style="text-align: left;">-0.4175</td>
<td style="text-align: left;">1.6173</td>
<td style="text-align: left;">0.1504</td>
<td style="text-align: left;">0.6603</td>
</tr>
<tr class="odd">
<td style="text-align: left;">large</td>
<td style="text-align: left;">1.9840</td>
<td style="text-align: left;">1.1282</td>
<td style="text-align: left;">1.3529</td>
<td style="text-align: left;">2.0273</td>
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
<td style="text-align: left;">-0.6290</td>
<td style="text-align: left;">0.6173</td>
<td style="text-align: left;">-0.3723</td>
<td style="text-align: left;">0.0168</td>
</tr>
<tr class="even">
<td style="text-align: left;">medium</td>
<td style="text-align: left;">-0.1112</td>
<td style="text-align: left;">-0.1790</td>
<td style="text-align: left;">0.0621</td>
<td style="text-align: left;">-0.1930</td>
</tr>
<tr class="odd">
<td style="text-align: left;">large</td>
<td style="text-align: left;">3.2936</td>
<td style="text-align: left;">-2.1955</td>
<td style="text-align: left;">1.4890</td>
<td style="text-align: left;">0.6173</td>
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
