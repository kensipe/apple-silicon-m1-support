# Apple Silicon M1 Development Support

As [Apple](https://www.apple.com/) has moved to Arm64  architecture with the release of [M1](https://en.wikipedia.org/wiki/Apple_M1) in 2020, I purchased an M1 mini to stay current and explore but wasn't in heavy dev mode on it. As Apple released the MBP Pro on M1 in 2021, I picked up an M1 Max targeted as my primary development machine.  I assumed that ~ 1 year of M1 in the wild + [Rosetta 2](https://appleinsider.com/inside/rosetta-2), good support would be in place... and I was wrong.   I'm opting for a GH repo vs a gist in order to collect PRs of other developers experiences and expectations as well.

The intend is to capture the issues, solutions and work arounds for a full-stack developer on the M1 architecture.

Another goal is to move away from the need for Rosetta for all the things!  More importantly is the need for things to work.

Happy to track other interest.  My interest is:

* Mobile support with XCode and Swift (no issues here of course)
* Java development (with Gradle)
* Front-end development with Node+
* Kubernetes Development with Docker, KinD and Minikube.
* Dev environment (terminal and utilities)
* Documentation / Business Tooling

## Not Currently Supported (Nov 21, 2021)

* Many Docker images [1]
* [divvy](https://mizage.com/divvy/) - likely to find another windows manager.  It's hard to find one that doesn't consume all the keymaps for a developer.
* [evernote](https://evernote.com/) - Lots of unanswered questions around M1 support.  This one is frustrating, it is the one tool I commonly have up that is NOT M1 optimized.  Starting this app, seems to create a process `com.apple.speech.speechsynthesisd` which hangs around after evernote is closed.
* Istio


## Work Arounds / Concerns

* [Powerlevel10k oh-my-zsh theme](p10k)
* [NodeJS](nodejs)
* Network [ports](monterey#ports)
* [Kubernetes](k8s)

## Odd and Needs Investigating

* After a crash, the process `CarbonComponentScannerXPC` and `chrome_crashpad_handler` showed up as "intel".

## Winners (Good Support)

* Apple Software (x-code, keynote, pages, etc.)
* [Docker for MacOS](https://docs.docker.com/desktop/mac/apple-silicon/) [1]
* [Homebrew](https://brew.sh/) [2]
* [Goland](https://www.jetbrains.com/go/) and [Intellij IDEA](https://www.jetbrains.com/idea/)
* [Chrome](https://www.google.com/chrome/) and [Microsoft Edge](https://www.microsoft.com/en-us/edge?r=1)
* [slack](https://slack.com/downloads/mac)
* [vscode](https://code.visualstudio.com/)
* [iterm2](https://iterm2.com/)
* [minikube](https://minikube.sigs.k8s.io/docs/start/)
* [KinD](https://kind.sigs.k8s.io/)
* [Postman](https://dl.pstmn.io/download/version/9.0.7/osx_arm64) [3]
* [Java 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html) Arm64 support is 17+
* [Golang 1.17.x](https://golang.org/dl/) Arm64 support is 1.16+



* [1] Docker runs natively on M1, however the container image eco-system is not complete.  For instance pulling `mysql` fails with: `no matching manifest for linux/arm64/v8 in the manifest list entries`
* [2] There is a surprise, and that is the homebrew Cellar has moved from `/usr` to `/opt`.  The path to cellar:  ` /opt/homebrew/Cellar/`
* [3] The postman link for M1 was hard to find and their site isn't up-to-date.  It appears that whatever the release version is (currently `9.0.7`) can be inserted into the url https://dl.pstmn.io/download/version/{version}/osx_arm64 for that versions M1 download.  Resulting in https://dl.pstmn.io/download/version/9.0.7/osx_arm64

