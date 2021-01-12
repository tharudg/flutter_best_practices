Folder Structure Conventions
============================

> Folder structure and naming conventions for flutter

### top-level directory 

  lib ──| 
        ├── blocs                   # Business Logics folders are contained here
        ├── models                  # Entity models
        ├── screens                 # Mobile screens
        ├── services                # Repository providers/services
        ├── shared                  # Shared widgets over the app
        ├── utils                   # support files
        └── main.dart

### second -level directory 

  blocs ──| 
          ├── Loading_bloc                 | 
          ├── Auth_bloc                  --| individual blocs which containes state chage logics
          ├── validator_bloc               |     
          └── barrell.dart         # exports all at once using brrell file
 
 Screens  ──| 
            ├── sign_in                 | 
            ├── sign_up               --| individual main screens with components specific to that screen
            ├── home                    |
            ├── profile                 |     
            └── barrell.dart         # exports all at once using brrell file
            
            
 
* Segregation of code into a proper folder structure namely providers, models, screens/pages, utils.
* Code is properly formatted with trailing commas used appropriately.
* Adequate comments added for documentation.
* Remove any print statements, unused and commented code
* Try to make code reusable with help of helper functions in utility files saved in the utils folder.
* Widgets should also be designed to be reusable and can be saved in a widgets folder separately.
* Avoiding static/hard coded strings in the UI screens. Constants should be derived from a single place 
  including color codes, validation messages etc. all saved in the constants file.
