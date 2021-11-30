# Coding Challenge at Auto1

## Screenshots
<a href="url"><img src="https://user-images.githubusercontent.com/35175271/143627484-bfc32b6d-b45d-4c1c-a54a-ec47657437e2.png" align="left" height="480" width="230" />
<a href="url"><img src="https://user-images.githubusercontent.com/35175271/143627766-e583c38c-e45b-4d56-811c-10f196dfa31b.png" align="left" height="480" width="230" />
<a href="url"><img src="https://user-images.githubusercontent.com/35175271/143628755-1f6524ac-76ed-44ac-a163-2a25e734b76f.png" align="left" height="480" width="230" />
<a href="url"><img src="https://user-images.githubusercontent.com/35175271/143630385-a007f372-9b4e-4408-ac5b-166374bbe101.png" align="left" height="480" width="230" />
<a href="url"><img src="https://user-images.githubusercontent.com/35175271/143632552-5d515429-4cf3-4e4e-8029-277da76be22b.png" align="left" height="480" width="230" />
<a href="url"><img src="https://user-images.githubusercontent.com/35175271/143634491-2a258373-9e8f-46d1-9dee-8192a9f577a0.png" align="left" height="480" width="230" />
<a href="url"><img src="https://user-images.githubusercontent.com/35175271/143637124-0c302027-780b-4c5a-a2de-29abfe49747d.png" align="left" height="480" width="230" /><
<a href="url"><img src="https://user-images.githubusercontent.com/35175271/143769602-c1104dd2-4a20-4372-a280-3b773cb963fe.png" align="left" height="280" width="600" />



![paging3-library-architecture](https://user-images.githubusercontent.com/35175271/143643932-9165fa8f-4ce7-44a5-9c65-170c2ccd52e1.png)
## Paging 3 architecture (without RemoteMediator)

## Architecture
MVVM

## Third-party libraries
- Architecture: Paging, Lifecycle, LiveData, Navigation, ViewModel, AppCompat, Android KTX
- UI component: Material
- Data Binding
- Coroutine, Flow
- Dependency injector: Hilt
- Networking: Retrofit, Moshi
- Unit testing: JUnit4, AssertJ, MockitoKotlin, Espresso Arch core testing (InstantTaskExecutorRule), Kotlinx coroutines test
- UI testing: Espresso
- Full list: https://github.com/Th3Alch3m1st/Auto1CodingChallenge/blob/master/buildSrc/src/main/java/Dependencies.kt

## performance
- Adapter data is cached in viewmodel scope. On Orientation change UI states is restored without making api call.
- Different Grid span handled on orientation changes, In Potrait Mode 2 Grid item loaded and In Landscape mode 3 grid item loadded.

## Idea for improvement
- For Tabloit a diffrent UI could be handled. For example, screen could be divided into three part to load three diffent fragment in a single UI state.
- Single Viewmodel and repository could be shared between all fragments, but it will break Single Responsibility and Interface Segregation rule, which may cause problems if applications need to be maintained in the long run.

## Build tools
- Android Studio Arctic Fox | 2020.3.1 Patch 3
- Gradle 7.0.2

## Troubleshoot
1. Get the error when compiling
Gradle plugin requires Java 11 but IDE uses Java 1.8 ![required-java11](https://user-images.githubusercontent.com/35175271/144035750-16757d5e-2fa1-4e9a-8007-9ca0d8ba1239.png)

One of a solution is going to Android Studio Preferences->Built, Execution, Deploymeny->Built Tools->Gradle-> Gradle Project and select Java 11 and try to compile again
![select-java-11](https://user-images.githubusercontent.com/35175271/144036093-103e7a65-52cf-4e56-b39b-5d4fbfcda64a.png)
