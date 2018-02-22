# Building LevelDB On Windows

## Prereqs 

Install the [Windows Software Development Kit version 7.1](https://www.microsoft.com/en-us/download/confirmation.aspx?id=8279).

If you are running Windows 10 follow these steps :

1. Uninstall any Visual C++ 2010 Redistributables from the control panel first. 
2. Download the corresponding offline [ISO image](http://download.microsoft.com/download/F/1/0/F10113F5-B750-4969-A255-274341AC6BCE/GRMSDKX_EN_DVD.iso) from the Windows SDK archive.
3. After mounting the image, open F:\Setup\SDKSetup.exe directly

Download and extract the [Snappy source distribution](https://codeload.github.com/google/snappy/legacy.tar.gz/master)

1. Open the "Windows SDK 7.1 Command Prompt" :
   Start Menu -> "Microsoft Windows SDK v7.1" > "Windows SDK 7.1 Command Prompt"
2. Change the directory to the leveldb project

## Building the Static lib 

* 32 bit Version 

        setenv /x86
        msbuild.exe /p:Configuration=Release /p:Platform=Win32 /p:Snappy=..\snappy-1.0.5

* 64 bit Version 

        setenv /x64
        msbuild.exe /p:Configuration=Release /p:Platform=x64 /p:Snappy=..\snappy-1.0.5


## Building and Running the Benchmark app

* 32 bit Version 

	    setenv /x86
	    msbuild.exe /p:Configuration=Benchmark /p:Platform=Win32 /p:Snappy=..\snappy-1.0.5
		Benchmark\leveldb.exe

* 64 bit Version 

	    setenv /x64
	    msbuild.exe /p:Configuration=Benchmark /p:Platform=x64 /p:Snappy=..\snappy-1.0.5
	    x64\Benchmark\leveldb.exe

