# Tutorial: Setting up VScode Server and Code Tunnel in a HPC Cluster

## Introduction
In this tutorial, we will walk through the steps to download and install VScode Server in a HPC cluster. We will also learn how to use Code Tunnel to establish a secure connection between VScode on our local machine and the VScode Server running in the HPC cluster.

## Prerequisites
Before we begin, make sure you have VScode installed in your local machine

## Step 1: Download and Install VScode Server
1. Download the VScode Server executable running this command in the cluster:
    ```
    curl -Lk 'https://code.visualstudio.com/sha/download?build=stable&os=cli-alpine-x64' --output vscode_cli.tar.gz
    ```

2. Extract the downloaded exectutable file:
    ```
    tar -xf vscode_cli.tar.gz
    ```
3. Add the VScode Server executable to your PATH:
    ```
    export PATH=$PATH:/your/path/to/vscode-server-package/
    ```
## Step 2: Configure Code Tunnel
1. On your local machine, open VScode.

2. Check if the Code Tunnel extension is already installed.

3. Open the Command Palette (Ctrl+Shift+P) and search for "Remote-tunnels: Add Tunnel".

4. You may now be promped to authenticate with your GitHub account.

## Step 3: Connect to VScode Server via Code Tunnel

1. On the cluster, start an interactive session with genD (not genD interactive), and activate your environment

2. Start the tunnel with the following command:
    ```
    code tunnel
    ```
3. Follow the instructions to authenticate with GitHub

4. On your local machine, open the Command Palette (Ctrl+Shift+P) and search for "Remote-tunnels: Connect to tunnel".

 VScode will establish a secure connection to the VScode Server running in the HPC cluster through GitHub.

## Conclusion
The main advantage of using VScode Server is that you can integrate it with Github copilot to get code suggestions and completions. You can have a free subscription to Copilot if you are a student or have a Github Pro account.

## Additional Resources
- [Code Tunnel Extension Documentation](https://code.visualstudio.com/docs/remote/tunnels#_using-the-code-cli)
