# Csharp Project structure guide

This document illustrates some of these common practices in organizing .NET projects, to help you structure your applications in a cleaner and easily understandable way.

## Folder Structure

```na
/
|__build/
    |__some_build_scripts.sh
|__docs/
    |__some_markdown_doc.md
|__samples/
    |__Sample1/
        |__sample1.md
        |__Sample1.cs
        |__Sample1.csproj
|__src/
    |__MyApplication.UI/
        |__SomeUiClass.cs
        |__MyApplication.UI.csproj
    |__MyApplication.Server/
        |__Application.cs
        |__MyApplication.Server.csproj
    |__ ...
    |__
|__/tests
    |__MyApplication.UI.Tests/
        |__SomeUiClassTests.cs
        |__MyApplication.UI.Tests.csproj
    |__MyApplication.Server.Tests/
        |__ApplicationTests.cs
        |__MyApplication.Server.Tests.csproj
    |__ ...
|__.editorconfig
|__.gitignore
|__.gitattributes
|__LICENSE (optional)
|__nuget.config
|__README.md
|__{solution}.sln
```

Files such as the ones described above like the **solution (.sln)** file, **README** or .***gitignore*** are put on the **root** folder, while the **rest** of the content is organized inside some main subfolders:

- **build:** Contains build customization scripts
- **docs:** Contains documentation files
- **samples:** This is where you would place files that provide examples to users on how to use your code or library
- **src:** Contains the actual source code for the application (the various projects with their classes etc.)
- **tests:** Contains tests projects

## Naming conventions for projects and namespaces

From the name of a project it should be easy to understand the functionality of the code it contains. For instance, if a project contains math related operations, it would probably contain Math in its name.

Talking about naming conventions, we try to follow this:

- **ProductName.Component** (eg. MyApplication.Models)
  
In the case of subfolders within the same project, the namespaces of the files within the subfolders reflect the same hierarchical structure.
For example, in a MyApplication.DataAccess project, classes within a **SqlServer folder** would belong to a MyApplication.DataAccess.SqlServer namespace.

## Use multiple projects to separate macro functionality or layers

For maintenance, it is better to group major features or layers into different projects. For example: the FrontEnd should be put into a UI or Client project.

## Unit tests organization

The structure and naming convention of unit test projects should reflect those of the source code that it's being tested, usually with an addition of a Tests suffix to the names of projects and classes.

For instance, the MyApplication.Math project would be tested by a unit test project called MyApplication.Math.Tests. The unit tests for a class called Calculator would be found in a test class named CalculatorTests.
