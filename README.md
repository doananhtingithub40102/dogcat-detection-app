<div style="height: 10px" id="top"></div>

<div align="center">
   <h1 align="center">
   <img src="https://live.staticflickr.com/65535/53352389401_db454aec01_m.jpg" width="100" />
   <br>DOGCAT-DETECTION-APP</h1>
   <h3>◦ ► This web application is designed to detect dogs and cats in images using AI.</h3>
   <h3>◦ Developed with the software and tools below.</h3>

   [![HTML5][HTML5-img]][HTML5-url]
   [![CSS3][CSS3-img]][CSS3-url]
   [![JavaScript][JavaScript-img]][JavaScript-url]
   [![Prettier][Prettier-img]][Prettier-url]
   [![Bootstrap][Bootstrap-img]][Bootstrap-url]
   [![Vite][Vite-img]][Vite-url]
   [![React][React-img]][React-url]
   [![Axios][Axios-img]][Axios-url]

   [![ESLint][ESLint-img]][ESLint-url]
   [![SemVer][SemVer-img]][SemVer-url]
   [![Python][Python-img]][Python-url]
   [![JSON][JSON-img]][JSON-url]
   [![Flask][Flask-img]][Flask-url]
   [![Express][Express-img]][Express-url]
   <a href="https://docs.ultralytics.com/"><img src="https://live.staticflickr.com/65535/53353045080_20eb2fe827_n.jpg" alt="Ultralytics" height="19px" /></a>
</div>

---

<span id="table-of-contents"></span>
## 📖 Table of Contents
- [📍 Overview](#overview)
   - [🍔 Major Technology Stack](#major-technology-stack)
- [📦 Features](#features)
- [📂 Repository Structure](#repository-structure)
- [🧱 Main Modules](#main-modules)
- [🚀 Getting Started](#getting-started)
   - [📋 Dependencies](#dependencies)
   - [⚙️ Configuration](#configuration)
   - [🔧 Installation](#installation)
   - [🤖 Running application](#running-application)
- [🤝 Contributing](#contributing)
- [👏 Acknowledgments](#acknowledgments)
- [🌐 Live the app](#live-the-app)

---


<span id="overview"></span>
## 📍 Overview

► This is a web application that uses the YOLOv8 model to detect dogs and cats in images. It provides a user-friendly interface for users to upload images and get results in few seconds. YOLOv8 is a state-of-the-art model for object detection, segmentation, classification and pose estimation tasks. It is fast, accurate, and easy to use, making it an excellent choice for a wide range of vision AI applications.

<div align="center">
   <img src="https://live.staticflickr.com/65535/53884985092_b833090616_h.jpg" alt="homepage app" />
   <div><i>Homepage of the app</i></div>
</div>

<span id="major-technology-stack"></span>
### 🍔 Major Technology Stack

Major frameworks/libraries used to bootstrap your project:

* [![React][React-badge-img]][React-url]
* [![Bootstrap][Bootstrap-badge-img]][Bootstrap-url]
* [![Flask][Flask-badge-img]][Flask-url]
* <a href="https://docs.ultralytics.com/"><img src="https://live.staticflickr.com/65535/53353045080_20eb2fe827_n.jpg" alt="Ultralytics" height="25px" /></a>


<p align="right"><a href="#table-of-contents">Table of Contents</a></p>

---

<span id="features"></span>
## 📦 Features

► **Object Detection**: Utilizes the YOLOv8 model for efficient and accurate detection of dogs and cats in images.

► **User-Friendly Interface**: Provides a seamless and intuitive web interface for users to upload images and receive detection results.

► **Fast Processing**: The application leverages the speed of YOLOv8, ensuring quick results in just a few seconds.

► **Downloading Detected Images**: Your uploaded images after successfully regconized can be downloaded. These images include the boxes and labels based on detected results of them.

► **Responsive Design**: The frontend is designed to be responsive, ensuring a consistent experience across various devices.

<p align="right"><a href="#table-of-contents">Table of Contents</a></p>

---


<span id="repository-structure"></span>
## 📂 Repository Structure

```sh
└── dogcat-detection-app/
    ├── backend/
    │   ├── config/
    │   │   ├── allowed_origins.py
    │   │   ├── inference_args.py
    │   │   ├── route_urls.py
    │   │   └── yolo_models_paths.py
    │   ├── helpers/
    │   │   ├── json_response.py
    │   │   └── results_to_json.py
    │   ├── routes/
    │   │   └── detection.py
    │   ├── services/
    │   │   ├── ultralytics/
    │   │   │   ├── models/
    │   │   │   │   └── catdog_detection_yolov8s.pt
    │   │   │   └── yolo.py
    │   ├── main.py
    │   └── requirements.txt
    ├── frontend/
    │   ├── public/
    │   │   ├── assets/
    │   │   │   ├── icons/
    │   │   │   └── images/
    │   ├── src/
    │   │   ├── _root/
    │   │   │   ├── pages/
    │   │   │   └── RootLayout.jsx
    │   │   ├── api/
    │   │   │   ├── axios.js
    │   │   │   └── routeURLs.js
    │   │   ├── components/
    │   │   ├── redux/
    │   │   │   ├── slices/
    │   │   │   ├── selectors.js
    │   │   │   └── store.js
    │   │   ├── utils/
    │   │   ├── App.jsx
    │   │   ├── globals.css
    │   │   └── main.jsx
    │   ├── .eslintrc.cjs
    │   ├── index.html
    │   ├── package-lock.json
    │   ├── package.json
    │   ├── vercel.json
    │   └── vite.config.js

```

<p align="right"><a href="#table-of-contents">Table of Contents</a></p>

---


<span id="main-modules"></span>
## 🧱 Main Modules

<details closed>
   <summary>Root</summary>

   #### backend/
   File                                         | Summary |
   | ---                                        | ---
   | [main.py][BE/main.py]                      | ► This file serves as the main entry point for the Flask web application. It registers the `detection_routes` blueprint for handling the detection API. |
   | [detection.py][BE/routes/detection.py]     | ► This file defines the detection routes as a Flask blueprint `detection_routes`. It includes an endpoint `/api/detect` for receiving POST requests with image data. Upon receiving an image, it uses the YOLOv8 model to perform object detection and returns the results in JSON format. |
   | [yolo.py][BE/services/ultralytics/yolo.py] | ► The `YOLOv8` class in this file encapsulates the YOLOv8 model from the Ultralytics library. The `predict` method utilizes the YOLOv8 model to perform object detection on the image, returning the results in a JSON-compatible format. |
   

   #### frontend/
   File                                                            | Summary |
   | ---                                                           | ---
   | [main.jsx][FE/src/main.jsx]                                   | ► Entry point for rendering the React app. |
   | [UploadImage.jsx][FE/src/comps/UploadImage.jsx]   | ► This component is used to upload images from user by browsing from their device, use ctrl+v to paste from the clipboard, or drag and drop an image into the app. |
   | [DetectObject.jsx][FE/src/_root/pages/DetectObject.jsx] | ► Once your image is uploaded on the homepage, our application will automatically navigate to route path `/detect-objects`, and then sending the image to AI model and infering detection results, after that the user can see the detected objects highlighted with bounding boxes and labels directly on the image. |
   | [canvasUtils.js][FE/src/utils/canvasUtils.js]                 | ► This file contains utility functions for drawing images and bounding boxes on an HTML canvas. |

</details>

<p align="right"><a href="#table-of-contents">Table of Contents</a></p>

---

<span id="getting-started"></span>
## 🚀 Getting Started

Getting started with the DOGCAT-DETECTION-APP is easy! Before you dive into the installation process, make sure you have the necessary dependencies installed on your system.

<span id="dependencies"></span>
### 📋 Dependencies

`- Git`: Version control is essential for managing the source code. Install Git by following the instructions [here][Git-url].

`- Python (3.x)`: The backend of the application is built using Python. Make sure you have Python installed on your machine. You can download it [here][Python-dl-url].

`- Node.js and npm`: Node.js is used for tools and utilities, and npm is the default package manager for Node.js. They are used to install and manage the frontend dependencies. The Node.js installer includes the NPM package manager, so you can install it [here][Nodejs-url].

Now, let's set up the necessary configurations before running the application:

<span id="configuration"></span>
### ⚙️ Configuration

1. **Environment Variables:**
   - Create a `.env` file in the root of the `backend` directory.
   - Add the following key-value pairs, specifying your desired host and port:
     ```env
     HOST=your_preferred_host (ex: HOST="localhost")
     PORT=your_preferred_port (ex: PORT=5000)
     ```
2. **Download YOLOv8 Model:**
   - Downloading the pre-trained YOLOv8 model that used for object detection. You can find and download the model i trained on my public [Google Drive](https://drive.google.com/file/d/1KUrWmrZLSy1W4bgaSKI-VFkgcORx-p7M/view?usp=drive_link) link with the file extension `.pt`. Place the downloaded model in a directory accessible by the backend. Update the path in the `config/yolo_models_paths.py` file if needed.

Now that you have configured the environment variables and downloaded the YOLOv8 model, follow the steps below to set up the project and run the web application on your local machine.

<span id="installation"></span>
### 🔧 Installation

1. Clone the Repository:
```sh
git clone https://github.com/doananhtingithub40102/dogcat-detection-app
```

2. Change to the Project Directory:
```sh
cd dogcat-detection-app
```

3. Install Backend Dependencies:
```sh
pip install -r backend/requirements.txt
```

4. Install Frontend Dependencies:
```sh
cd frontend
npm install
```

Now that you have set up the project, you can run the DOGCAT-DETECTION-APP on your local machine.

<span id="running-application"></span>
### 🤖 Running application

5. Run the Backend Server:
```sh
# In CMD, navigate to the backend directory and run this command
python main.py
```
The server will start and listen for incoming requests based on the specified `HOST` and `PORT` in your `.env` file. And you should see a message: ***`'Welcome to Dog and Cat Detection web application'`*** on your web browser by the URL address `http://[your_preferred_host]:[your_preferred_port]`. It indicates that the backend server is running.

6. Run the Frontend Development Server:
```sh
# In CMD, navigate to the frontend directory and run this command
npm run dev
```
The frontend development server will start, and you can access the application by navigating to `http://127.0.0.1:5173` or `http://localhost:5173` in your web browser.

<p align="right"><a href="#table-of-contents">Table of Contents</a></p>

---

<span id="contributing"></span>
## 🤝 Contributing

Contributions are welcome! Here are several ways you can contribute:

- **[Submit Pull Requests][submit-pull-requests]**: Review open PRs, and submit your own PRs.
- **[Join the Discussions][join-the-discussions]**: Share your insights, provide feedback, or ask questions.
- **[Report Issues][report-issues]**: Submit bugs found or log feature requests for DOANANHTINGITHUB40102.

#### *Contributing Guidelines*

<details closed>
<summary>Click to expand</summary>

1. **Fork the Repository**: Start by forking the project repository to your GitHub account.
2. **Clone Locally**: Clone the forked repository to your local machine using a Git client.
   ```sh
   git clone <your-forked-repo-url>
   ```
3. **Create a New Branch**: Always work on a new branch, giving it a descriptive name.
   ```sh
   git checkout -b new-feature-x
   ```
4. **Make Your Changes**: Develop and test your changes locally.
5. **Commit Your Changes**: Commit with a clear and concise message describing your updates.
   ```sh
   git commit -m 'Implemented new feature x.'
   ```
6. **Push to GitHub**: Push the changes to your forked repository.
   ```sh
   git push origin new-feature-x
   ```
7. **Submit a Pull Request**: Create a PR against the original project repository. Clearly describe the changes and their motivations.

Once your PR is reviewed and approved, it will be merged into the main branch.

</details>

<p align="right"><a href="#table-of-contents">Table of Contents</a></p>

---

<span id="acknowledgments"></span>
## 👏 Acknowledgments

I extend my appreciation to the following organizations for their invaluable contributions to this project:

- **Ultralytics HUB**: Special thanks to [Ultralytics][Ultralytics-url] for providing an excellent platform that hosts essential resources for computer vision models and datasets.

   - **YOLOv8 Model Information**: Explore detailed information about the YOLOv8 model used in this project on the [Ultralytics HUB][Ultralytics-model].

   - **Training Dataset**: The success of the YOLOv8 model is attributed to the high-quality training dataset. For more insights into the dataset used for training, visit the [Ultralytics HUB][Ultralytics-dataset].

- **Vercel**: We acknowledge [Vercel][Vercel-url] for providing a seamless and free deployment platform. Our application is hosted and made accessible to users through Vercel's platform.

<p align="right"><a href="#table-of-contents">Table of Contents</a></p>

---

<span id="live-the-app"></span>
## 🌐 Live the app

Experience the Dog and Cat Detection web application in action! Visit the live deployment and try out the features:

**[Live Demo](https://dogcat-detection-app.vercel.app/)**

<p align="right"><a href="#top">Back to top</a></p>

---

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

<!-- Software and tools links & images -->
[HTML5-img]: https://img.shields.io/badge/HTML5-E34F26.svg?style=flat-square&logo=HTML5&logoColor=white
[HTML5-url]: https://developer.mozilla.org/en-US/docs/Web/HTML

[CSS3-img]: https://img.shields.io/badge/CSS-1572B6.svg?style=flat-square&logo=CSS3&logoColor=white
[CSS3-url]: https://developer.mozilla.org/en-US/docs/Web/CSS

[JavaScript-img]: https://img.shields.io/badge/JavaScript-F7DF1E.svg?style=flat-square&logo=JavaScript&logoColor=black
[JavaScript-url]: https://developer.mozilla.org/en-US/docs/Web/javascript

[Prettier-img]: https://img.shields.io/badge/Prettier-F7B93E.svg?style=flat-square&logo=Prettier&logoColor=black
[Prettier-url]: https://prettier.io/docs/en/index.html

[Bootstrap-img]: https://img.shields.io/badge/Bootstrap-7952B3.svg?style=flat-square&logo=Bootstrap&logoColor=white
[Bootstrap-badge-img]: https://img.shields.io/badge/Bootstrap-563D7C.svg?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com/

[Vite-img]: https://img.shields.io/badge/Vite-646CFF.svg?style=flat-square&logo=Vite&logoColor=white
[Vite-url]: https://vitejs.dev/guide/

[React-img]: https://img.shields.io/badge/React-61DAFB.svg?style=flat-square&logo=React&logoColor=black
[React-badge-img]: https://img.shields.io/badge/React-61DAFB.svg?style=for-the-badge&logo=React&logoColor=black
[React-url]: https://react.dev/

[Axios-img]: https://img.shields.io/badge/Axios-5A29E4.svg?style=flat-square&logo=Axios&logoColor=white
[Axios-url]: https://axios-http.com/docs/intro

[ESLint-img]: https://img.shields.io/badge/ESLint-4B32C3.svg?style=flat-square&logo=ESLint&logoColor=white
[ESLint-url]: https://eslint.org/docs/latest/

[SemVer-img]: https://img.shields.io/badge/SemVer-3F4551.svg?style=flat-square&logo=SemVer&logoColor=white
[SemVer-url]: https://semver.org/

[Python-img]: https://img.shields.io/badge/Python-3776AB.svg?style=flat-square&logo=Python&logoColor=white
[Python-url]: https://www.python.org/doc/
[Python-dl-url]: https://www.python.org/downloads/

[Git-url]: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

[Nodejs-url]: https://nodejs.org/

[JSON-img]: https://img.shields.io/badge/JSON-000000.svg?style=flat-square&logo=JSON&logoColor=white
[JSON-url]: https://www.json.org/json-en.html

[Flask-img]: https://img.shields.io/badge/Flask-000000.svg?style=flat-square&logo=Flask&logoColor=white
[Flask-badge-img]: https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white%29
[Flask-url]: https://flask.palletsprojects.com/

[Express-img]: https://img.shields.io/badge/Express-000000.svg?style=flat-square&logo=Express&logoColor=white
[Express-url]: http://expressjs.com/

[Ultralytics-url]: https://www.ultralytics.com/hub
[Ultralytics-model]: https://hub.ultralytics.com/models/3pkwjukNl2EBtw2kuvJl
[Ultralytics-dataset]: https://hub.ultralytics.com/datasets/8H38sOMZB5vwQNU0cO56

[Vercel-url]: https://vercel.com/

<!-- Github links -->
[BE/main.py]: https://github.com/doananhtingithub40102/dogcat-detection-app/blob/main/backend/main.py
[BE/routes/detection.py]: https://github.com/doananhtingithub40102/dogcat-detection-app/blob/main/backend/routes/detection.py
[BE/services/ultralytics/yolo.py]: https://github.com/doananhtingithub40102/dogcat-detection-app/blob/main/backend/services/ultralytics/yolo.py

[FE/src/main.jsx]: https://github.com/doananhtingithub40102/dogcat-detection-app/blob/main/frontend/src/main.jsx
[FE/src/comps/UploadImage.jsx]: https://github.com/doananhtingithub40102/dogcat-detection-app/blob/main/frontend/src/components/UploadImage.jsx
[FE/src/_root/pages/DetectObject.jsx]: https://github.com/doananhtingithub40102/dogcat-detection-app/blob/main/frontend/src/_root/pages/DetectObject.jsx
[FE/src/utils/canvasUtils.js]: https://github.com/doananhtingithub40102/dogcat-detection-app/blob/main/frontend/src/utils/canvasUtils.js

[submit-pull-requests]: https://github.com/doananhtingithub40102/dogcat-detection-app/blob/main/CONTRIBUTING.md
[join-the-discussions]: https://github.com/doananhtingithub40102/dogcat-detection-app/discussions
[report-issues]: https://github.com/doananhtingithub40102/dogcat-detection-app/issues
