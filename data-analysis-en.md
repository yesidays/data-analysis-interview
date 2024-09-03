
# Data Analysis Questions
Common questions and answers about data analysis and SQL.

### What is a dataset?
A dataset is a collection of data, generally organized in the form of a table with rows and columns, where each row represents an individual record and each column represents a feature or variable of those records.

### What is the difference between structured and unstructured data?
Structured data is highly organized and has a predictable format (such as SQL databases), which facilitates its analysis. Unstructured data is more disorganized and can include formats such as free text, videos, images, and emails, which require additional processing to extract useful information.

### What is a histogram and what is it used for?
A histogram is a type of bar chart that represents the distribution of a numerical variable by grouping data into intervals. It is used to get an overview of the data distribution, identify centrality, dispersion, and the presence of any bias in the data.

### Explain what data cleaning is and why it is important.
Data cleaning involves the processes of detecting and correcting (or removing) corrupt or inaccurate data from a dataset. It is crucial because incorrect or incomplete data can lead to erroneous conclusions and negatively affect the quality of the analysis results.

### What is an "outlier" and how can it affect your analysis?
An "outlier" is a data point that differs significantly from other data in a dataset. It can be the result of an error or natural variation. Outliers can affect the outcome of statistical analyses and predictive models, distorting means, standard deviations, and other statistical measures.

### How is linear regression performed and what do you interpret from its results?
Linear regression is a statistical analysis that attempts to model the relationship between a dependent variable and one or more independent variables by specifying a linear equation. From its results, we interpret the coefficient for each independent variable that indicates how it affects the expected value of the dependent variable, as well as the R-squared value which measures how well the data fit the model.

### What are clustering methods and what are some common examples?
Clustering methods are unsupervised machine learning techniques that group a set of objects in such a way that objects in the same group (or cluster) are more similar to each other than to those in other groups. Common examples include K-means, hierarchical clustering, and DBSCAN.

### Explain what Principal Component Analysis (PCA) is and how it is used in data analysis.
Principal Component Analysis (PCA) is a dimensionality reduction technique that transforms a set of possibly correlated variables into a smaller set of uncorrelated variables called principal components. PCA is used to simplify the complexity in high-dimensional data sets while preserving as much information as possible.

### What is supervised learning and how does it differ from unsupervised?
Supervised learning is a machine learning technique that learns a model from labeled input data, attempting to predict outputs for new instances based on that learning. In contrast, unsupervised learning works with unlabeled data and is used to find patterns or intrinsic structures in the data without explicit instructions on what is being looked for.

### How is cross-validation used in building predictive models and what is its main benefit?
Cross-validation is a model evaluation method that involves dividing a data set into multiple subsets and iteratively training and testing on these. The main benefit of cross-validation is that it provides a robust measure of model performance and helps prevent overfitting, ensuring that the model is generalizable to new data.

# Basic SQL Questions

### How do you create subsets or filter data in SQL?
To create subsets or filter data in SQL, I use the `WHERE` clause. This clause allows specifying conditions that the rows must meet to be selected. For example, `SELECT * FROM customers WHERE age > 30;` selects all rows in the `customers` table where the `age` column is greater than 30.

### What is the difference between the WHERE and HAVING clauses in SQL?
The main difference between `WHERE` and `HAVING` in SQL is that `WHERE` is used to filter rows before group aggregations are performed, while `HAVING` is used to filter groups after they have been formed and aggregate functions have been calculated. For example, `WHERE` is used to filter individual records, such as `SELECT * FROM sales WHERE quantity > 2;`. In contrast, `HAVING` is used in queries that involve aggregate functions, like `SELECT vendor_id, COUNT(*) FROM sales GROUP BY vendor_id HAVING COUNT(*) > 10;`, where vendors with more than 10 sales are filtered.

### How do you write a stored procedure in SQL?
A stored procedure in SQL is a set of SQL instructions that you can define and store in the database to be executed multiple times. Here I show you a basic example of how to write one in SQL Server:
```sql
CREATE PROCEDURE sp_GetEmployeeData 
  @EmployeeID INT
AS
BEGIN
  SELECT FirstName, LastName, JobTitle
  FROM Employees
  WHERE EmployeeID = @EmployeeID;
END;
```
This stored procedure, called `sp_GetEmployeeData`, takes an input parameter `@EmployeeID`, and returns the first name, last name, and job title of a specific employee from the `Employees` table.
