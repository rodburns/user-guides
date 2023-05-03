# Profiling

This is an adaptation of [Capturing IPU Reports](https://docs.graphcore.ai/projects/graph-analyser-userguide/en/latest/user-guide.html#capturing-ipu-reports).

## Reports

### Capturing IPU Reports

See [Capturing IPU Reports](https://docs.graphcore.ai/projects/graph-analyser-userguide/en/latest/user-guide.html#capturing-ipu-reports) for more information.

This section describes how to generate the files that the Graph Analyser can analyze. The Graph Analyser uses report files generated during compilation and execution by the Poplar SDK.

### IPU Memory Overhead

Because of all these extra memory requirements, a model with high memory consumption may go out of memory when profiling is enabled. Depending on the model, you can adjust its parameters to leave space for the instrumentation. For example, you can try decreasing the batch size. In TensorFlow BERT you can adjust the micro batch-size.

### Host Computing Overhead

It is essential that you also try to reduce the iterations on each run. For instance, by reducing the number of steps or the number of batches per step you can get a lighter execution profile. This will not only reduce the host computation overhead but will also speed up visualization in the Graph Analyser.

## Download PopVision

1. Download [PopVision Tools](https://www.graphcore.ai/developer/popvision-tools).

2. Click **Download Now** button.

3. In the **Graph Analyser** section, select you operating system.

### Ubuntu OS

To install .AppImage files on Ubuntu, you can follow these steps:

Download the .AppImage file that you want to install.

Open the terminal by pressing Ctrl + Alt + T.

Navigate to the directory where the .AppImage file is located. You can use the cd command to change the directory. For example, if the file is located in the Downloads folder, you can navigate to that folder by running cd ~/Downloads.

Make the .AppImage file executable by running the following command: **chmod +x popvision-graph-analyser-3.14.0.AppImage**.

Run the .AppImage file by typing **./popvision-graph-analyser-3.14.0.AppImage** in the terminal.

The application should now be launched. If you want to install it system-wide, you can right-click on the .AppImage file, select Properties, then go to the Permissions tab and check the box that says "Allow executing file as program". After that, you can move the .AppImage file to a location such as /opt or /usr/local/bin to make it available system-wide.

PopVision Graph Analyser is running.

## Create SSH Session

Use **ssh** from your development system.

The **ssh** command will use a **jumphost** and **port forwarding**.  The format is as follows:

```bash
ssh -J ALCFUserID@gc-login-dd.ai.alcf.anl.gov ALCFUserID@gc-poplar-DD -L 8090:127.0.0.1:22
ssh -J wilsonb@gc-login-01.ai.alcf.anl.gov wilsonb@gc-poplar-02.ai.alcf.anl.gov -L 8090:127.0.0.1:22
ssh wilsonb@gc-login-01.ai.alcf.anl.gov -L 8090:127.0.0.1:22
```

Where:

| Argument            | Help |
|---------------------|------------------------------|
| ALCFUserID          | Is your ALCF user identification.   |
| dd                  | Is the Graphcore login node to use, i.e., 01 or 02 |
| DD                  | Is the Graphcore node to use, i.e., 02, 03, or 04.   |
| 8090                | Is the port on your local machine.   |
| 127.0.0.1:22        | Is the local IP address and port on the remote machine. |
|  |  |  |

> **Note**: You will need to provide a MobilePASS+ authentication twice.

You will receive a prompt.

## User Interface

![Graph Analyser](files/Graph_Ananlyser_main.png "Graph Analyser")

![Graphcore System View](files/image.png "Graphcore System View")

1. Click **Open a report...**;
2. Click the **remote** tab;
3. Enter your **ALCFUserID** for remote machine;
4. Enter the **Hostname** of your local machine, i.e., 127.0.0.1;
5. Enter your **Port** address used in the **ssh** command, e.g., 8090;
6. Click **Connect**;
7. Navigate to your reports directory;
8. Select the **training** directory;
9. Select **archive.a** file; and
10. Click **Open** button.

The **Summary Report** will be displayed.
