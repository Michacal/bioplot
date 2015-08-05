Settings
========

EER
---
To include the EER in a Zoo plot's legend, set the following variable to True in the [zoo] section: ::

    [zoo]
    ; Show EER values
    showEerValues = True

Cllr
----
To include the Cllr in a Zoo plot's legend, set the following variable to True in the [zoo] section: ::

    [zoo]
    ; Show min Cllr values
    showMinCllrValues = True


min Cllr
--------
To include the minimum Cllr in a Zoo plot's legend, set the following variable to True in the [zoo] section: ::

    [zoo]
    ; Show min Cllr values
    showMinCllrValues = True


bioplot.cfg
----------- 
There are many, many more settings. Have a look at this list what they entaili (edit this list with a text editor like notepad, textedit or vi only)::

    ; This file contains flags and values used by bioplot.py
    ; All values here are defaults also contained in the program itself.
    ; You can use this file to change the program's default behaviour.
    ;
    ; Note: all options are CaSe sensitive !
    
    ; Copyright (C) 2014, 2015 Jos Bouten ( josbouten at gmail dot com )
    
    ; This program is free software; you can redistribute it and/or modify
    ; it under the terms of the GNU General Public License as published by
    ; the Free Software Foundation; either version 2 of the License, or
    ; (at your option) any later version.
    
    ; This program is distributed in the hope that it will be useful,
    ; but WITHOUT ANY WARRANTY; without even the implied warranty of
    ; MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    ; GNU General Public License for more details.
    
    ; You should have received a copy of the GNU General Public License along
    ; with this program; if not, write to the Free Software Foundation, Inc.,
    ; 51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.
    
    
    [cfg]
    ; If set to True 'allowDups' allows for both scores in a symmetric trial to be used.
    ; This means that the score of P vs Q and the score of Q vs P is used.
    ; Otherwise only the first encountered in the raw scores is used.
    allowDups = False
    
    ; Choose a colormap: Spectral, gist_ncar, hsv, gist_rainbow or prism
    colorMap = hsv
    
    ; set debug flag to True: will print a lot of info which might be of use
    ; when trying to debug the code.
    debug = False
    
    ; Show config info at start of program on commandline
    showConfigInfo = True
    
    ; Path to dir where results and plots are stored.
    outputPath = output
    
    ; Are we running on OSX or not?
    runningOSX = False

    ; Are we running on Microsoft Windows or not?
    ; The Labels by default show black text on a yellow background.
    ; The yellow background may be too large for the text.
    ; If so, set runningWindows to True, this will change the yellow
    ; background into a grey one and make the background fit the text in size.
    runningWindows = False

    ; Save all scores to text file separated in target and non target scores per meta value.
    saveScores = True 
    
    [data]
    ; minimum value we expect for a score in type3 data.
    minimum4Type3 = -1.0E+99
    ; maximum value we expect for a score in type3 data.
    maximum4Type3 = 1.0E+99
    
    ; minimum value we expect for a score in type2 data.
    minimum4Type2 = -1.0E+99
    ; maximum value we expect for a score in type2 data.
    maximum4Type2 = 1.0E+99
    
    ; minimum value we expect for a score in type1 data.
    minimum4Type1 = -1.0E+99
    ; maximum value we expect for a score in type1 data.
    maximum4Type1 = 1.0E+99
    
    [zoo]
    ; Show ellipses at position of data points representing standard deviation of target and non target scores
    ; as published by Alexander et al. @ IAFPA conference Zurich, Switserland, 2014
    alexanderStyle = True
    
    ; Show labels for data points within quartile ranges
    annotateQuartileMembers = True
    
    ; Add target and non target score histogram to zoo plot
    boutenStyle = True
    
    ; Show histogram of shift of points depending on meta data values.
    showCircularHistogram = True
    
    ; Show Cllr values
    showCllrValues = True

    ; Show min Cllr values
    showMinCllrValues = True

    ; Show EER values
    showEerValues = True
    
    ; Draw lines between labels with opposing metadata values
    interconnectMetaValues = True
    
    ; Limit the std dev values of average non target and average target scores within +- 3 * std dev.
    limitStdDevs = True
    
    ; When True will prevent the use of x-axis labels in the histograms added to the zoo plot.
    noHistAnnot = False
    
    ; Opacity can be from 0 to 1 for small to large ellipses
    ; Restrict it to a portion of the range.
    opacityLimitFactor = 0.85
    
    ; If we add labels to the command line, we dimm al the none matching points and
    ; ellipses by this factor thus making the given labels more prominent.
    dimmingFactor = 0.8
    
    ; Scale data to screen resolution. 150 should be good for 1600x1024 ... 1280x1024
    ; Make smaller if you want bigger ellipses.
    scaleFactor = 150
    
    ; Show all annotations when starting program; one click on the figure will make them disappear.
    ; Will only work if interconnectMetaValues is set to False.
    showAnnotationsAtStartup = False
    
    ; Show reference ellipses or not.
    showReference = True
    
    ; Do not show text with reference ellipses
    showTextAtReferenceAtStartup = False
    
    ; Show kernel in zoo histogram
    showKernelInHist = True
    
    ; Show mean of average target and non target points as a black dot.
    showUnitDataPoint = True
    
    ; Give distinct colors to data points within quartile ranges. This is only done when the
    ; metadata field contains only one distinct value.
    useColorsForQuartileRanges = True
    
    ; Big ellipses may overshadow smaller ones at the same position.
    ; Using opacity makes the smaller ones visible again.
    useOpacityForBigEllipses = False
    
    ; Use vertical axis as proposed by Yager et al.
    ; When set to False the y-axis will be inversed.
    yagerStyle = True
    
    [layout]
    ; bottom_h = left_h = zleft + zwidth + spacing
    ; rectZoo = [zleft, zbottom, zwidth, zheight]
    ; rectHistx = [zleft, bottom_h, zwidth, xheight]
    ; rectHisty = [left_h, zbottom, ywidth, zheight]
    
    ; Left bottom x-position of zoo plot in boutenZoo
    zLeft = 0.05
    
    ; Width of zoo plot
    zWidth = 0.65
    
    ; Left bottom y-position of zoo plot in boutenZoo
    zBottom = 0.05
    
    ; Height of zoo plot in boutenZoo
    zHeight = 0.63
    
    ; Height of top histogram in boutenZoo
    xHeight = 0.2
    
    ; Width of right hand side histogram in boutenZoo
    yWidth = 0.2
    
    ; Spacing between zoo plot and left side of histograms in boutenZoo
    spacing = 0.02
    
    [histogram]
    nrBins = 150
    
    ; Normalize histogram
    normHist = True
    
    ; Show meta data values in histogram
    showMetaInHist = True
    
    [accuracy]
    nrPoints = 100
    
    [ranking]
    nrPoints = 100
    
    maxNrSteps = 100
    
    [matrix]
    ; Not working at the moment:
    ; In the cross identification plot, we want at least
    ; this number of scores per label, otherwise skip
    ; the label.
    ; minNrScores4MatrixPlot = 25
    
    ; color map of the plot
    matrixColorMap = Greys
    
    ; When set to True: combine matrices (if there are multiple
    ; because of different meta values) in a square or oblong matrix,
    ; otherwise make a horizontal bar or vertical column of matrices.
    combineMatrices = True

    ; Show labels at tick marks
    showMatrixLabels = True
    
    ; rotate xtick labels at a degree
    labelAngle = 70
    
    [probability]
    ; Number of threshold values used to calculate P(defense)
    ; and P(prosecution) from target and non target scores
    ; per meta value.
    nrSamples4Probability = 500