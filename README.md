<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Two-Stage Anomaly Detection in Personalized Healthcare using SVM &amp; SVR</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        background-color: #f9f9f9;
        color: #333;
        line-height: 1.6;
        padding: 20px;
      }
      h1 {
        color: #2c3e50;
      }
      h2 {
        color: #34495e;
        border-bottom: 1px solid #ddd;
        padding-bottom: 5px;
      }
      h3 {
        color: #34495e;
      }
      ul {
        margin-left: 20px;
        margin-bottom: 20px;
      }
      table {
        width: 100%;
        border-collapse: collapse;
        margin-bottom: 20px;
      }
      table, th, td {
        border: 1px solid #ddd;
        padding: 8px;
      }
      th {
        background-color: #f2f2f2;
        text-align: left;
      }
      code {
        background-color: #eee;
        padding: 2px 4px;
        border-radius: 3px;
      }
    </style>
  </head>
  <body>
    <h1>Two-Stage Anomaly Detection in Personalized Healthcare using SVM &amp; SVR</h1>
    <p>
      This repository contains the implementation of a two-stage anomaly detection model for wireless body area networks (WBANs), designed for personalized healthcare monitoring. The approach leverages Support Vector Machines (SVM) for anomaly classification and Support Vector Regression (SVR) for contextual anomaly detection. The method effectively distinguishes between sensor malfunctions and actual medical emergencies, ensuring high accuracy in anomaly detection.
    </p>
    
    <h2>📌 Key Features</h2>
    <ul>
      <li>
        <strong>Two-stage anomaly detection:</strong>
        <ul>
          <li>SVM for point anomaly classification</li>
          <li>SVR for contextual anomaly detection</li>
        </ul>
      </li>
      <li>
        <strong>Feature Engineering:</strong>
        <ul>
          <li>Average Heart Rate</li>
          <li>Heart Rate Difference</li>
          <li>ECG Rolling Mean &amp; Standard Deviation</li>
          <li>MinMax Scaling for feature normalization</li>
        </ul>
      </li>
      <li>Dynamic thresholding based on machine learning techniques</li>
      <li>Achieves up to 99.59% accuracy in anomaly detection</li>
      <li>Handles real-world physiological data for early medical intervention</li>
    </ul>
    
    <h2>Dataset</h2>
    <p>
      The dataset consists of 72,000 physiological readings from 16 individuals (12 healthy participants and 4 patients), recorded thrice daily over five days. Data includes:
    </p>
    <ul>
      <li><strong>Physiological attributes:</strong> Body Temperature, Heart Rate (from two sensors), SpO2, ECG.</li>
      <li><strong>Anomaly labels:</strong> anomaly (overall anomaly classification), first (point anomalies), and second (contextual anomalies).</li>
    </ul>
    
    <h2>📊 How It Works</h2>
    <h3>1️⃣ Data Preprocessing</h3>
    <ul>
      <li>Reads the <code>modified_output.csv</code> dataset.</li>
      <li>Assigns unique Person_IDs.</li>
      <li>Labels individuals as Healthy (Person_ID ≤ 12) or Patient (Person_ID &gt; 12).</li>
      <li>Splits data into training (healthy individuals) and testing (patients + remaining healthy individuals).</li>
    </ul>
    
    <h3>2️⃣ Feature Engineering</h3>
    <p>Extracts relevant health metrics such as:</p>
    <ul>
      <li>Heart Rate Average &amp; Difference</li>
      <li>ECG Rolling Mean &amp; Standard Deviation</li>
    </ul>
    
    <h3>3️⃣ Anomaly Detection</h3>
    <p>The two-stage detection process includes:</p>
    <ul>
      <li>
        <strong>SVM Classification:</strong> Initially classifies anomalies using a radial basis function (RBF) kernel.
      </li>
      <li>
        <strong>SVR-Based Contextual Analysis:</strong> Builds regression models for physiological attributes and detects anomalies based on residual errors.
      </li>
    </ul>
    
    <h3>4️⃣ Evaluation</h3>
    <ul>
      <li>Overall anomaly detection</li>
      <li>Point anomaly detection</li>
      <li>Contextual anomaly detection</li>
    </ul>
    
    <h3>Performance Metrics</h3>
    <table>
      <thead>
        <tr>
          <th>Model</th>
          <th>Accuracy (%)</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Proposed (SVM + SVR)</td>
          <td>99.59%</td>
        </tr>
        <tr>
          <td>DBSCAN + KMeans</td>
          <td>60.01%</td>
        </tr>
        <tr>
          <td>SVM (Standalone)</td>
          <td>69.29%</td>
        </tr>
        <tr>
          <td>Linear Regression</td>
          <td>60.00%</td>
        </tr>
      </tbody>
    </table>
    
    <h2>Funding Agency</h2>
    <p>
      This research is supported by BITS Bio-CyTiH Foundation and Department of Science and Technology (DST), Government of India. Their contributions have been instrumental in the development of this anomaly detection framework for wireless body area networks (WBANs) in personalized healthcare.
    </p>
  </body>
</html>
