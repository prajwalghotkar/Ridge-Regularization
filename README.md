# Ridge Regularization
---
**Regularization is a technique in machine learning and statistics used to prevent overfitting and improve the generalization of models. Overfitting occurs when a model learns not only the underlying patterns in the training data but also its noise and random fluctuations, leading to poor performance on unseen data. Regularization works by adding a penalty to the loss function used to train the model, discouraging it from fitting the noise and encouraging simpler, more robust models.**
---
##### Types of Regularization
- There are three main types of regularization commonly used in linear regression:

##### 1. Ridge Regularization (L2 Regularization)
##### 2. Lasso Regularization (L1 Regularization)
##### 3. Elastic Net Regularization
--- 

##### 1. Ridge Regularization (L2 Regularization)
- Ridge regularization adds a penalty equivalent to the square of the magnitude of coefficients to the loss function. Mathematically, the loss function becomes:
![prajwal_data](https://github.com/user-attachments/assets/63725e60-3664-412b-bc87-9da74b497b03)

- Loss=MSE+λj=1∑pwj2

where:
- MSE is the mean squared error,
- wj are the model coefficients (weights),
- λ is the regularization parameter controlling the strength of the penalty.

##### How Ridge Regularization Works
- Ridge regularization adds the squared magnitude of the coefficients as a penalty term to the loss function during model training.
- The strength of the penalty is controlled by λ When λ=0, it is equivalent to ordinary least squares. As λ increases, the flexibility of the model decreases, reducing overfitting.
- All coefficients are shrunk toward zero, but none are set exactly to zero. This is why, unlike Lasso, Ridge maintains all features but reduces their impact.
![prajwal_data](https://github.com/user-attachments/assets/5a1e7602-22da-47db-a059-4afb09dd08bc)


##### Intuition
- In high-dimensional data or when features are highly correlated, ordinary least squares can result in unstable coefficients with high variance.
- Ridge addresses this by shrinking coefficients, thus reducing variance at the cost of introducing some bias (bias-variance trade-off).
- It is particularly effective in situations where many features contribute a little to the target, as in the diabetes dataset.

##### Ridge Regression with the Diabetes Dataset
- Suppose you want to use Ridge regression on the diabetes dataset (available in scikit-learn). Here’s an outline of the code and the intuition behind each step:

##### Code Intuition
- Data splitting is done to test how well our model generalizes to unseen data.
- Ridge Regularization (with alpha=1.0) adds a penalty to the loss function for large coefficients, shrinking them and thus controlling model complexity.
- The fit method trains the model while considering both the ordinary least squares loss and the regularization penalty.
- The mean squared error (MSE) tells how well the model predicts the outcome; a lower MSE indicates better generalization.
- The resulting model coefficients will be smaller in magnitude compared to an unregularized model, reducing the risk of overfitting.

##### When to Use Ridge Regularization
- When you have high-dimensional data (many features).
- When you suspect multicollinearity among your features.
- When you want to keep all features in your model, but reduce their overall influence.

![WhatsApp Image 2025-08-02 at 15 21 25_0c5c2158](https://github.com/user-attachments/assets/926c1afa-5abc-405e-ba25-7d0f453ac143)
![WhatsApp Image 2025-08-02 at 15 21 25_485b6151](https://github.com/user-attachments/assets/2405a1e6-1c41-43fd-8c84-a5a074e89a0a)

