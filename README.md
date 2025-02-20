<h1 align="center">ARDL Cointegration and ECM Analysis</h1>

<p align="center">
    <em>A Python function to perform ARDL cointegration analysis and estimate the Error Correction Model (ECM).</em>
</p>

<h2>Overview</h2>
<p>
This Python function performs ARDL cointegration analysis and estimates the ECM model. It helps in:
<ul>
    <li>Selecting optimal lags using the AIC criterion (if <code>exog_orders</code> is not provided).</li>
    <li>Estimating the Unrestricted Error Correction Model (UECM).</li>
    <li>Providing long-run (cointegrating) and short-run (ECM) model summaries.</li>
    <li>Plotting ARDL residuals (Error Correction Term - ECT), default error diagnostics, and CUSUM plots with 95% confidence bands.</li>
</ul>
</p>

<h2>Features</h2>
<ul>
    <li>Automatic or manual lag selection for ARDL models.</li>
    <li>Estimation of UECM and ECM models.</li>
    <li>Long-run and short-run model summaries.</li>
    <li>Comprehensive error diagnostics and stability tests (CUSUM).</li>
</ul>

<h2>Requirements</h2>
<p>To run this function, you need the following libraries:</p>
<ul>
    <li><code>pandas</code></li>
    <li><code>numpy</code></li>
    <li><code>matplotlib</code></li>
    <li><code>statsmodels</code></li>
</ul>

<h2>Usage</h2>
<pre>
<code>
# Import necessary libraries
import pandas as pd
from statsmodels.tsa.ardl import ardl_select_order, UECM
import statsmodels.api as sm
import matplotlib.pyplot as plt
import warnings

# Call the ARDL function
ardl_model(
    dataset=dataframe,
    y="dependent_variable",
    X=["independent_variable1", "independent_variable2"],
    max_lag=4,
    exog_orders=None  # or provide a list of lag orders for exogenous variables
)
</code>
</pre>

<h2>Function Parameters</h2>
<ul>
    <li><code>dataset</code>: The dataset as a Pandas DataFrame.</li>
    <li><code>y</code>: The dependent variable (string).</li>
    <li><code>X</code>: List of independent variable(s).</li>
    <li><code>max_lag</code>: Maximum lag order for selection.</li>
    <li><code>exog_orders</code>: List of manually determined lag orders for exogenous variable(s). If <code>None</code>, the function automatically selects lags.</li>
</ul>

<h2>Output</h2>
<ul>
    <li>The UECM (unconstrained) model</li>
    <li>Long-run (cointegrating) model summary</li>
    <li>Short-run (ECM) model summary</li>
    <li>Plot of the ARDL residuals (ECT)</li>
    <li>Plot of default error diagnostics</li>
    <li>The CUSUM plots with 95% confidence bands</li>
</ul>

<h2>Example</h2>
<pre>
<code>
# Example usage
import pandas as pd

# Load your dataset
df = pd.read_csv("your_dataset.csv")

# Run the ARDL model
ardl_model(
    dataset=df,
    y="Y_variable",
    X=["X1", "X2", "X3"],
    max_lag=3,
    exog_orders=None
)
</code>
</pre>

<h2>Notes</h2>
<ul>
    <li>If <code>exog_orders</code> is not provided, the function will automatically select the optimal lags using the AIC criterion.</li>
    <li>Ensure that your dataset is free of missing values, as NA values can cause errors during lagging.</li>
    <li>Use <code>exog_orders</code> to manually specify lag orders if the automatic selection fails.</li>
</ul>

<h2>License</h2>
<p>
This project is licensed under the <a href="https://opensource.org/licenses/MIT">MIT License</a>.
</p>

<h2>Author</h2>
<p>
Developed by <strong>Patrick Onodje</strong>. Feel free to reach out for any questions or collaborations on <strong>patrickonodje@live.com</strong>.
</p>
