![Banner](https://github.com/csgoh/roadmapper/blob/main/images/roadmapper-banner.png?raw=true)

[![license](https://img.shields.io/badge/license-mit-brightgreen.svg?style=plastic)](https://en.wikipedia.org/wiki/MIT_License)
![release](https://img.shields.io/pypi/v/roadmapper)
![Wheel](https://img.shields.io/pypi/wheel/roadmapper?style=plastic)
![download count](https://img.shields.io/pypi/dm/roadmapper?style=plastic)
![code size](https://img.shields.io/github/languages/code-size/csgoh/roadmapper?style=plastic)
![commit count](https://img.shields.io/github/commit-activity/m/csgoh/roadmapper?style=plastic)
[![CodeFactor](https://www.codefactor.io/repository/github/csgoh/roadmapper/badge)](https://www.codefactor.io/repository/github/csgoh/roadmapper)
![python version](https://img.shields.io/pypi/pyversions/roadmapper?style=plastic)
![CI](https://github.com/csgoh/roadmapper/actions/workflows/ci.yaml/badge.svg)

# Roadmaper - a Roadmap as Code (RaC) Tool

## Purpose
The purpose of roadmapper python library is used to draw roadmap by using python code. This is the first Roadmap as Code (RaC) library. RaC helps to create and edit roadmap in a more efficient way without having to use any graphical tools that are not always easy to use to create or update a roadmap.

With git repository like GitHub or Bitbucket, roadmaps created using RaC can be version controlled, track changes and can be easily shared with others.

### Latest version
![release](https://img.shields.io/pypi/v/roadmapper)

:book: For usage documentation, how-to guide and code examples, refer to [Roadmapper Wiki](https://github.com/csgoh/roadmap-generator/wiki).

View the [Change Logs](https://github.com/csgoh/roadmapper/wiki/Change-Logs) to find out the latest updates and additions in the most recent version.

![multilingual roadmappper](https://github.com/csgoh/roadmapper/blob/main/images/roadmapper-banner-multilingual.png?raw=true)

### Python version requirements:
* Python 3.10+
  
### Library Dependencies
* python-dateutil >= 2.8.2
* Pillow >= 10.0.0
* drawsvg >= 2.2.0


Any feedback or suggestions are welcome. Please feel free to create an issue or pull request.
<br/>
<hr>


## Installation
### Install from PyPI
```bash
pip install roadmapper
```
### Upgrade to the latest version
If you are running older version of roadmap-generator, you can upgrade to the latest version by running the following command:
```bash
pip install --upgrade roadmapper
```

<hr>

## Documentation
Please refer to [Roadmapper Wiki](https://github.com/csgoh/roadmap-generator/wiki) for more information on how to use this RaC library.

<br/>
<hr>

## Code Example
:point_right: Note: In order for the following code to work, you will need to download the `matariki-tech-logo.png` file to your local storage. The png file can be downloaded in the `\images\logo\` folder.

```python 
from roadmapper.roadmap import Roadmap
from roadmapper.timelinemode import TimelineMode

roadmap = Roadmap(1200, 400, colour_theme="BLUEMOUNTAIN")
roadmap.set_title("My Demo Roadmap")
roadmap.set_subtitle("Matariki Technologies Ltd")
roadmap.set_timeline(TimelineMode.MONTHLY, start="2023-01-01", number_of_items=12)
roadmap.add_logo("matariki-tech-logo.png", "top-right", 50, 50)

group = roadmap.add_group("Core Product Work Stream")

task = group.add_task("Base Functionality", "2023-01-01", "2023-10-31")
task.add_milestone("v.1.0", "2023-02-15")
task.add_milestone("v.1.1", "2023-08-01")

parellel_task = task.add_parallel_task("Enhancements", "2023-11-15", "2024-03-31")
parellel_task.add_milestone("v.2.0", "2024-03-30")

task = group.add_task("Showcase #1", "2023-03-01", "2023-05-07")
task.add_parallel_task("Showcase #2", "2023-06-01", "2023-08-07")

roadmap.set_footer("Generated by Roadmapper")
roadmap.draw()
roadmap.save("demo01.png")
```

### Output

![Roadmapper](https://github.com/csgoh/roadmapper/blob/main/images/demo01.png?raw=true)




