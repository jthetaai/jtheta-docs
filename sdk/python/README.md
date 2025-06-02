
# 📦 JTheta Python SDK

The official Python SDK for interacting with the [JTheta.ai](https://jtheta.ai) platform — enabling seamless dataset management, annotation requests, and automation of your AI pipeline.

---

## 🚀 Installation

Install the SDK using pip:

```bash
pip install jtheta
```

[![PyPI version](https://badge.fury.io/py/jtheta.svg)](https://pypi.org/project/jtheta/)

---

## 🔑 Getting Started

1. **Login** to [https://app.jtheta.ai](https://app.jtheta.ai) and create a workspace.
2. Navigate to the workspace dashboard and click on the **Create API Key** option in the left sidebar.
3. Copy the generated API key.

```python
import jtheta

# Initialize with your API key
jtheta.init("your_api_key_here")

# Validate your API key
print(jtheta.validate_key())
```

---

## 📁 Project & Dataset Management

### Create a New Project

```python
project = jtheta.create_project("My Project", "image")
```

### Create a Dataset and Upload Images

```python
dataset = jtheta.create_dataset(
    "MyDataset",
    "MIT",
    "My Project",
    ["image1.jpg", "image2.jpg"]
)
```

### Upload Additional Images

```python
upload_image = jtheta.upload_images(
    231,
    "My Project",
    "image1.jpg"
)
```

---

## 👥 Manage Annotators & Reviewers

### Retrieve Annotators

```python
annotators = jtheta.get_annotators()
```

### Retrieve Reviewers

```python
reviewers = jtheta.get_reviewers()
```

---

## 📝 Request Annotations

```python
jtheta.request_annotation(
    "My Project",
    dataset["id"],
    "annotator@example.com",
    "reviewer@example.com",
    [
        {"label": "car", "type": "Bounding Boxes"},
        {"label": "truck", "type": "Polygons"}
    ],
    allow_class_creation=True,
    auto_annotation=False
)
```

---

## 📥 Download Annotated Dataset

```python
jtheta.download_dataset(
    dataset["id"],
    format="csv",
    version="1.0",
    save_path="annotations.csv"
)
```

---

## ✅ Features

- Project and dataset creation
- Image upload
- Annotation request and monitoring
- Dataset export
- Retrieve annotators and reviewers

---

## 📬 Support & Feedback

Have questions or feature requests? Reach out!

- **Email**: [contact@jtheta.ai](mailto:contact@jtheta.ai)
- **Website**: [https://jtheta.ai](https://jtheta.ai)

---

## 📝 License

This project is licensed under the MIT License. See the [LICENSE](https://pypi.org/project/jtheta/) file for details.
