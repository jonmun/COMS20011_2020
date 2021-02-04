# COMS20011_2020 Labs

The labs are all Jupyter Notebooks.  Please get set up with them as soon as possible: I've left Lab 1 up to allow you to test.

There are two basic options: remotely logging in to a lab machine or locally installing Python (not supported).

## Remote access to MVB machines

#### Option 1 (Linux Remote Desktop; Windows/Linux)
First, follow these instructions to set up the [VPN](https://uob.sharepoint.com/sites/itservices/SitePages/vpn-connect.aspx). Then, follow these guidelines provided by IT Services to set up a [Linux Remote Desktop](https://uob.sharepoint.com/sites/itservices/SitePages/fits-engineering-linux-x2go.aspx).  Should work on Mac, but apparently the required XQuartz software doesn't work well.  This is supported by IT, so any issues with this software can be sent to service-desk@bristol.ac.uk.

#### Option 2 (X Remote Desktop; Linux)
If you are running an X server already (i.e. because you're running Linux locally), then open a shell on your machine, and type this command: 
```
ssh -X -J youruserid@seis.bris.ac.uk youruserid@rd-mvb-linuxlab.bristol.ac.uk
```
This method will not work on Windows Linux Subsystem (WSL), you can use Option 3 in WSL, or Option 1 in Windows, instead.

#### Option 3 (SSH Port forwarding; WSL/Linux/Mac)
If you can get it working, this method will give the lowest latency.

This allows you to open Jupyter Notebook in a browser on your local machine while still running it on a lab machine.

1. Map a free port on your machine (e.g. 6006) to a free port on the lab machine (e.g. 7373)
```
ssh -L 6006:localhost:7373 -J user@seis.bris.ac.uk user@rd-mvb-linuxlab.bristol.ac.uk
```
       
2. Run Jupyter Notebook on the port mapped to your local machine: 7373
```
/opt/anaconda3-4.4.0/bin/jupyter notebook --no-browser --port 7373
```
      
3. Open localhost:6006 in a web browser on your local machine and enter the token provided by Jupyter Notebook.

## Locally installing Anaconda

*This is not supported!*

Follow instructions in:
[https://www.anaconda.com/products/individual](https://www.anaconda.com/products/individual)

## Starting a Notebook on the lab machines:
Open a terminal, and enter:
```
/opt/anaconda3-4.4.0/bin/jupyter notebook
```
Jupyter should automatically open a webpage. If not, open your favourite web browser and go to: localhost:8888/notebooks.
