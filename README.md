# Sec-2 Subject Allocation Exercise

## Overview
This repository provides a solution for teachers to efficiently allocate subjects to a cohort of approximately 200 students based on predefined criteria. It simplifies and optimizes the allocation process, saving significant time and effort.

## Prerequisites
Before using this script, ensure that you have:
- Basic knowledge of Python (for using the script) OR
- Use .exe for those without familiarity with Python
- Access to the required external resources:
  - **[Google Drive Folder](https://drive.google.com/drive/u/1/folders/18R6k7c44Y1uMyx99rdclAFxVkA8oJuz9)**
  - **[RJCAT Website](https://www.rjcat.com/solutions)**

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/String-sg/Sec-2-Subject-Allocation-Exercise-GitHub.git
   cd Sec-2-Subject-Allocation-Exercise-GitHub
   ```
2. Ensure you have Python installed (>= 3.x).

## Usage
1. Edit the appended excel templates as needed with your data
2. Run the following command to allocate subjects automatically:
   ```bash
   python "Python Script_deferred_acceptance_with_displacement_final4.py"
Open an Github issue or reach out via Discord/ WhatsApp if you encounter any problems!

## Features
- **Automated Allocation**: Quickly assigns subjects to students based on the defined priorities.
- **Scalable**: Handles large cohorts of around 200 students.
- **[Coming soon] Customizable via python script**: these are mostly hard coded at the moment into `read_student_data`, `read_course_data`, and try_place_student_in_course / `deferred_acceptance_with_displacement`. Eventual customizations could include:
- RankMethod = TotalScore|Weighted|Custom
- TieBreakOrder = Math,English,Science
- Displacement = GroupWide|CourseOnly|None
- GroupCapMode = GroupOnly|GroupAndCourse

## Contributing
We welcome contributions from the community. To contribute:
1. Fork the repository.
2. Create new features or bug fixes in a dedicated branch.
3. Submit a pull request for review.