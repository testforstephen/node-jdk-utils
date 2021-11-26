This is changelog of node-jdk-utils project.

## 0.2.0
### Added
- New API **getRuntime(homedir, options)**: verify if given directory is a valid runtime, and provide more information if it is.  
- Export type defitions for better usablity.

## 0.1.0
### Added
- New API **findRuntimes(options)**: list all Java runtimes installed on local machine. It searches locations deducted from environment variables (PATH/JAVA_HOME/JDK_HOME), SDKMAN installation directory, jEnv configurations, and default installation locations of popular distributions.