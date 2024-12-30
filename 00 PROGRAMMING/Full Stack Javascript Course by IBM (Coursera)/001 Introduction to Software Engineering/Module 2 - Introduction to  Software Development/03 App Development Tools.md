> [!info] Version Control
> - Keeps track of:
> 	- What changes were made
> 	- When they were made
> 	- Who made them
> - Resolve change conflicts
> - Provides a way to revert to an older version
> - Examples:
> 	- Git
> 	- Github

> [!abstract] Libraries
> - __Collections of reusable code__
> - Multiple code libraries can be integrated into a project
> - Codes can be called when required
> - Can solve specific problems or add specific features
>> [!example] Examples of code libraries are:
>> - __jQuery__: a JavaScript library that simplifies DOM manipulation
>> - __Email-validator__: checks if email address is correctly constructed and valid
>> - __Apache Commons Proper__: a repository of reusable Java components

> [!abstract] Frameworks
> - Provides a ___standard way___ to build and deploy applications
> - __Acts as a skeleton__ you extend by adding your own code
> - Should be determined and used from the beginning
> - Dictates the architecture of the app
> - Calls your code
> - Allow you ___less control than libraries___
> 
>> [!example] 
>> - __AngularJS__ is a JavaScript-based framework for dynamic web applications
>> - __Vue.js__ is a Javascript framework focused on the user interface
>> - __Django__ is a framework that uses Python for web development


> [!info] Inversion of control
> ![[Pasted image 20241215002356.png]]

> [!info] CI/CD
> - __Continuous Integration__ with ___Continuous Delivery___ or Continuous Deployment
> - Enables developers to deliver frequent changes reliably
> - Implemented through a build-automation server
> - CI automatically builds and tests code
> - CD deploys the changes

> [!info] Build Tools
> - Transform source code into binaries for installation
> - Important in environments with many inter-connected projects and multiple developers
> - __Automate tasks__ like:
> 	- Downloading dependencies
> 	- Compiling source code into binary code
> 	- Packaging that binary code
> 	- Running tests
> 	- Deployment to production systems
> - Initiate a build from the command line or from an IDE
> - Two categories that are widely used:
> 	- Build-automation __utilities__
> 		- generates build artifacts like _executables_, by compiling and linking source code
> 	- Build-automation __servers__
> 		- executes __Build-automation utilities__ on scheduled or triggered basis.
>> [!example] Some example of build tools
>> - Webpack: a module bundler for JavaScript
>> - Babel: a JavaScript compiler
>> - Web Assembly: a binary instruction format that runs in your browser


> [!info] Packages
> - Packages make apps easy to install
> - Packages contain
> 	- App files
> 	- Instructions for installation
> 	- Metadata
> 
>> [!tip] Package managers
>> - __To distribute packages__
>> - Make working with packages easier
>> - Coordinate with file archivers to extract package archives
>> - Verify checksums and digital certificates to ensure the integrity and authenticity of the package
>> - Locate, download, install, or update existing software from a software repository
>> - Manage dependencies to ensure a package is installed with all packages it requires
>>> [!example] Package managers by platform
>>>  Some commonly used package managers for the major platforms are:
>>>  - ___Linux___
>>> 	 - Debian Package Management System (DPKG)
>>> 	 - Red Hat Package Manager (RPM)
>>>  - ___Windows___
>>> 	 - Chocolatey
>>>  - ___Android___
>>> 	 - Package Manager
>>>  - ___MacOS___
>>> 	 - Homebrew
>>> 	 - MacPorts
>>> 
>>>  - ___Cloud application___ package Managers
>>> 	 - Manages Libraries and Utility Code
>>> 		 - __Node.js / JavaScript__
>>> 			 - npm
>>> 		 - __Java__
>>> 			 - Gradle
>>> 			 - Maven
>>> 		 - __Ruby__
>>> 			 - RubyGems
>>> 		 - __Python__
>>> 			 - Pip
>>> 			 - Conda



