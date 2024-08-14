Here's a `README.md` file that you can include in your GitHub repository to describe the project and guide users on how to deploy and use it.

---

## MonkeyPox Classification Web App

This project demonstrates a simple web application that uses a TensorFlow.js model to classify images as part of a MonkeyPox detection system. The model is hosted on Azure Blob Storage, and the web application is hosted via Azure Static Web Apps.

### Features

- **Image Upload**: Users can upload an image from their local device.
- **Image Display**: The uploaded image is displayed on the web page.
- **Inference**: The app uses a pre-trained TensorFlow.js model to predict the classification of the uploaded image.
- **Result Display**: The prediction results are displayed on the web page.

### Prerequisites

Before you start, make sure you have:

- An Azure Storage Account with the `model.json` and associated weight files uploaded to a publicly accessible Blob Storage container.
- A GitHub account to host the HTML and JavaScript files.
- Basic knowledge of HTML and JavaScript.

### Setup Instructions

#### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

#### 2. Update the Model URL in `index.html`

Open the `index.html` file and update the following line with the correct URL to your `model.json` file in Azure Blob Storage:

```javascript
const modelUrl = 'https://<your-storage-account-name>.blob.core.windows.net/<container-name>/model.json';
```

Replace `<your-storage-account-name>` and `<container-name>` with your actual Azure Storage account name and container name.

#### 3. Push Changes to GitHub

After making the necessary updates, commit the changes and push them to your GitHub repository:

```bash
git add .
git commit -m "Updated model URL"
git push origin main
```

#### 4. Deploy to Azure Static Web Apps

1. Go to the [Azure portal](https://portal.azure.com/) and create a new **Static Web App**.
2. Link the Static Web App to your GitHub repository.
3. Azure will automatically build and deploy your web application.
4. Once the deployment is complete, Azure will provide a public URL for your web app.

#### 5. Access the Web Application

Visit the provided URL to access your deployed web application. You should see the web interface where you can upload an image, trigger the model to make predictions, and view the results.

### Usage

1. **Upload an Image**: Click on the "Choose File" button to upload an image.
2. **Display the Image**: The uploaded image will be displayed on the screen.
3. **Predict**: Click the "Predict" button to run the model on the uploaded image.
4. **View Results**: The prediction results will be displayed below the image.

### Troubleshooting

- **Model Not Loading**: Ensure that the model files in Azure Blob Storage are publicly accessible and the URL in `index.html` is correct.
- **Cross-Origin Errors**: Check the CORS settings for your Azure Storage account to ensure requests from the web app are allowed.
- **Prediction Issues**: If predictions aren't working as expected, use the browser's developer console to check for any JavaScript errors.

### Contributing

If you'd like to contribute to this project, please fork the repository and use a feature branch. Pull requests are warmly welcome.

### License

This project is licensed under the MIT License.
