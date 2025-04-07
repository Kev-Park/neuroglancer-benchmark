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

To install the correct version of Chromedriver, visit [this installation page](https://googlechromelabs.github.io/chrome-for-testing/) and copy the correct installation link for your Chrome version and OS. Download the provided **.zip** file and unzip it in the root folder of your development folder.

Keep in mind you may have to install new Chromedriver versions if your Chrome installation updates; we hope to roll out an alternative system for Chrome + Chromedriver versioning for the future.

## Environment Setup

Next, create a `config.json` file, also in the root folder of your development folder. You may either copy the example file provided in the Github repo, or copy the JSON content here: 

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

For the sake of this tutorial, we will leave `default_ngl_start_url`, `default_middle_auth_start_url`, `window_width`, `window_height`, `model_image_width`, and `model_image_height` at their default values. The rest of the fields, however, should be filled with user-specific information.

Fill in `google_email_address` and `google_password`; this information will provide access to neuron data in Neuroglancer.

Next, fill in `driver_path_mac`, `driver_path_win` or `driver_path_linux` **and** `chrome_binary_path_linux` depending on what operating system you will be running this tutorial on. The driver-related paths should provide access to the `chromedriver` executable that you downloaded in the installation guide. Note that you only have to fill in the path relevant to your system.

Linux users must also fill in `chrome_binary_path_linux` in addition to the driver path linking to their system's **Chrome** executable.

We can now begin writing some initial code to test the Python integrations with Neuroglancer.

## Code

In this example, we will be creating our `main.py` file in the same folder as our `config.json` and Chromedriver installation. We will configure `main.py` to start a Neuroglancer session and apply an arbitrary action of our choice to Neuroglancer in a loop before closing automatically. The finished `main.py` can be found at the bottom of this tutorial; we will now go through different components of the code.

First, import the installed integration code, in particular `Environment`, with `from ngllib import Environment`.

Next, we can **optionally** define an `options` dictionary to pass along certain preferences for how the `Environment` will collect and pass along information.

```
options = {
        'euler_angles': True,
        'resize': False,
        'add_mouse': False,
        'fast': True,
        'image_path': None
}
```

A more detailed overview of the accepted parameters for ``options`` (including default behavior for the `Environment` if `options` is not passed) can be found in [the references](./references.md). At a basic level, however, `euler_angles` defines whether or not we receive orientation in terms of Euler angles or quaternions; ``resize`` defines whether Neuroglancer screenshots (one of the state returns) are automatically resized; ``add_mouse`` overlays mouse location on top of the returned screenshots; ``fast`` overwrites the default Selenium screenshot method with a faster implementation; and `image_path` provides a save location for returned screenshots.

Next, it is possible to define a custom reward function instead of the default function provided in `ngllib`. Here, we define a function that returns a value of `1` after each step:

```
def custom_reward(state, action, prev_state):
    return 1, False
```

Additional information on defining a custom reward function can be found in [the references](./references.md). All reward functions must accept the updated state input (after action application), `state`, the recently applied action vector, `action`, and the state prior to action application, `prev_state`. They also must return two values: `reward` and `done`, the latter of which indicates if an episode is complete or not. In this example, because we will be inputting a finite number of actions to Neuroglancer, it is not necessary to code this behavior into our custom function.

Next, we can instantiate an `Environment` object with our `config.json` and `reward_function`:

`env = Environment(headless=False, config_path="config.json", verbose=False, reward_function=custom_reward)`

During training, it is possible to instantiate `Environment` with `headless=True` to hide the Chrome window. We will keep `headless=False` for now to validate our code.

We can now start a Neuroglancer session by calling `env.start_session(**options)`, passing along the ``options`` dictionary defined earlier containing our session-specific preferences.

We can now begin interacting with Neuroglancer! Here we run a short loop of 100 steps where we will rotate our 3D view while zooming out.

```
for i in range(100):
    
    # action_vector should reflect a model output; here it is hardcoded for demonstration purposes
    action_vector = [
        0, 0, 0,  # left, right, double click booleans
        100, 100,  # x, y
        0, 0, 0,  # no modifier keys
        1,  # no JSON change
        10, 0, 0,  # position change
        0,  # cross-section scaling
        0.2, 0, 0,  # orientation change in Euler angles, which is better for a model to learn or a human to understand
        2000  # projection scaling (log-scale in neuroglancer)
        ]
    
    _, reward, _, _ = env.step(action_vector)

    print(reward)
```

`env.step` returns multiple values which are detailed in [the references](./references.md); here we save `reward` to display the output of our custom reward function.

You should now have a basic understanding of how interactions with Neuroglancer are handled; feel free to read through the rest of the documentation for additional information. If you have any persisting questions, feel free to reach out to [raphael_levisse@berkeley.edu](mailto:raphael_levisse@berkeley.edu), [kp0374@princeton.edu](mailto:kp0374@princeton.edu) or [dl2635@princeton.edu](mailto:dl2635@princeton.edu).

## Complete `main.py`
```
from ngllib import Environment

# Initialize options for environmental interaction, including state return types
options = {
        'euler_angles': True,
        'resize': False,
        'add_mouse': False,
        'fast': True,
        'image_path': None
}

def custom_reward(state, action, prev_state):
    return 1, False

env = Environment(headless=False, config_path="config.json", verbose=False, reward_function=custom_reward)

env.start_session(**options)

for i in range(100):
    
    # action_vector should reflect a model output; here it is hardcoded for demonstration purposes
    action_vector = [
        0, 0, 0,  # left, right, double click booleans
        100, 100,  # x, y
        0, 0, 0,  # no modifier keys
        1,  # no JSON change
        10, 0, 0,  # position change
        0,  # cross-section scaling
        0.2, 0, 0,  # orientation change in Euler angles, which is better for a model to learn or a human to understand
        2000  # projection scaling (log-scale in neuroglancer)
        ]
    
    _, reward, _, json_state = env.step(action_vector)

```