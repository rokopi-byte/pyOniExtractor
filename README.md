# pyOniExtractor
frame extractor for OpenNI2 recordins .Oni

Command line tool for frame extraction from OpenNI2 .oni recording. It was tested in Ubuntu 16.04 and Windows 10. OpenNI2 library are contained in the folder lib and comes from Orbbec (version 26/03/2018).
This software save all frames contained in each available stream in the recording (specified as parameter -v) as png in the folder specified (argument -d) within a step (argument -i). Depth frames are saved in the original format (16bit grayscale) and in a more readable format, scaled to 8 bit and multiplied by a factor plus an offset (with also cast saturation). You can change this values in the code, they dependent by the max and min values of the depths.
Name of the saved images contain the frame ID, which in case of synchronization was enabled in the recording can be used to match color and depth frames.

Requirements:
Python 3 32bit, with the following packages (you can install them using pip):
openni
numpy
opencv 3 (opencv-python

Usage:

usage: frame_extractor.py [-h] -v VIDEO_PATH [-d DST] [-i INTERVAL]

optional arguments:
  -h, --help     show this help message and exit
  -v VIDEO_PATH  path Video (Required)
  -d DST         Destination Folder, default "img"
  -i INTERVAL    Interval, step of extraction, default 1
