---
layout: page
title: Getting Started
permalink: /startup-guide/
parent: Integration Documentation
---
# ❔ Getting Started

## Necessary Installations

First, clone the [integration code](https://github.com/seung-lab/ngl_bench). Afterwards, with a terminal open in the repository's root directory, you can run `pip install ./` to install the integration code as a library, called **ngllib**. If you wish to make changes to **ngllib**, run `pip install -e .'` to install the library in editable mode; edits will be immediately reflected at runtime.

Interactions with Neuroglancer are made through Chrome, through use of Selenium and Chromedriver.

Chromedriver **is not** installed by default when downloading Chrome. You must install the specific version of Chromedriver matching your current Chrome installation's version that also corresponds to your operating system. You can find your current Chrome version by launching Google Chrome and entering **chrome://version/** in the URL.

To install the correct version of Chromedriver, visit [this installation page](https://googlechromelabs.github.io/chrome-for-testing/) and copy the correct installation link for your Chrome version and OS. Download the provided *.zip* file and unzip it, ideally in root folder of your development folder.

Keep in mind you may have to install new Chromedriver versions if your Chrome install updates; we hole to roll out an alternative system for Chrome + Chromedriver versioning for the future.

## Environment Setup

Next, create a `config.json` file, also ideally in the root folder of your development folder. You may either copy the example file provided in the Github repo, or copy the JSON content here: 

```
{
    "default_ngl_start_url": "https://neuroglancer-demo.appspot.com/#!%7B%22dimensions%22:%7B%22x%22:%5B4e-9%2C%22m%22%5D%2C%22y%22:%5B4e-9%2C%22m%22%5D%2C%22z%22:%5B4e-8%2C%22m%22%5D%7D%2C%22position%22:%5B143944.703125%2C61076.59375%2C192.5807647705078%5D%2C%22crossSectionScale%22:2.0339912586467497%2C%22projectionOrientation%22:%5B-0.4705163836479187%2C0.8044001460075378%2C-0.30343097448349%2C0.1987067461013794%5D%2C%22projectionScale%22:13976.00585680798%2C%22layers%22:%5B%7B%22type%22:%22image%22%2C%22source%22:%22precomputed://https://bossdb-open-data.s3.amazonaws.com/flywire/fafbv14%22%2C%22tab%22:%22source%22%2C%22name%22:%22Maryland%20%28USA%29-image%22%7D%2C%7B%22type%22:%22segmentation%22%2C%22source%22:%22precomputed://gs://flywire_v141_m783%22%2C%22tab%22:%22source%22%2C%22segments%22:%5B%22%21720575940623044103%22%2C%22%21720575940607208114%22%2C%22720575940603464672%22%5D%2C%22name%22:%22flywire_v141_m783%22%7D%5D%2C%22showDefaultAnnotations%22:false%2C%22selectedLayer%22:%7B%22size%22:350%2C%22layer%22:%22flywire_v141_m783%22%7D%2C%22layout%22:%22xy-3d%22%7D",
    "default_middle_auth_start_url": "http://localhost:8000/client/#!%7B%22dimensions%22%3A%20%7B%22x%22%3A%20%5B4e-09%2C%20%22m%22%5D%2C%20%22y%22%3A%20%5B4e-09%2C%20%22m%22%5D%2C%20%22z%22%3A%20%5B4e-08%2C%20%22m%22%5D%7D%2C%20%22layers%22%3A%20%5B%7B%22source%22%3A%20%22precomputed%3A//https%3A//bossdb-open-data.s3.amazonaws.com/flywire/fafbv14%22%2C%20%22type%22%3A%20%22image%22%2C%20%22tab%22%3A%20%22source%22%2C%20%22name%22%3A%20%22Maryland%20%28USA%29-image%22%7D%2C%20%7B%22tab%22%3A%20%22segments%22%2C%20%22source%22%3A%20%22graphene%3A//middleauth%2Bhttps%3A//prodv1.flywire-daf.com/segmentation/1.0/flywire_public%22%2C%20%22type%22%3A%20%22segmentation%22%2C%20%22segments%22%3A%20%5B%22720575940595846828%22%5D%2C%20%22colorSeed%22%3A%20883605311%2C%20%22name%22%3A%20%22Public%20Release%20783-segmentation%22%7D%5D%2C%20%22position%22%3A%20%5B174232.0%2C%2068224.0%2C%203870.0%5D%2C%20%22showDefaultAnnotations%22%3A%20false%2C%20%22perspectiveOrientation%22%3A%20%5B0%2C%200%2C%200%2C%201%5D%2C%20%22projectionScale%22%3A%201500%2C%20%22crossSectionScale%22%3A%200.5%2C%20%22jsonStateServer%22%3A%20%22https%3A//globalv1.flywire-daf.com/nglstate/post%22%2C%20%22selectedLayer%22%3A%20%7B%22layer%22%3A%20%22annotation%22%2C%20%22visible%22%3A%20true%7D%2C%20%22layout%22%3A%20%22xy-3d%22%7D",
    "google_email_address": "YOURACCOUNT@gmail.com",
    "google_password": "YOURPASSWORD",

    "driver_path_mac": "PATHTOMACDRIVER",
    "driver_path_win": "PATHTOWINDOWSDRIVER",
    "driver_path_linux": "PATHTOLINUXDRIVER",
    "chrome_binary_path_linux": "PATHTOLINUXBINARY",

    "window_width": 1800,
    "window_height": 900,

    "model_image_width": 960,
    "model_image_height": 540
}
```

