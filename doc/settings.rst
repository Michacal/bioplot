.. _rst_settings:

Settings
========

settings file
-------------
Bioplot will read settings from the file bioplot.cfg by default. To use a different settings file use the -c option. ::

    python bioplot.py -c some_other_settings_file

The file bioplot.cfg contains many sections. Below for each section the variables are explained and for each the default value is shown.
To change the behaviour of bioplot, change the setting in the settings file. Misspelled options are ignored. By default bioplot will print
the values for all options on the command line when started. If you want to explicitly check them without making any plot or reading any data,
start bioplot like this: ::

    python bioplot.py -s

It will then show a list of chosen settings like so: ::

    Config info taken from 'default values':
    alexanderStyle = True, alwaysSave = True, allowDups = False, alpha4References = 1.0, alpha4UnitCircles = 0.5, animalColors = True, annotateEllipsesInQuartiles = False, boutenStyle = True, combineMatrices = True, debug = False, dimmingFactor = 0.8, interconnectMetaValues = True, labelAngle = 70, labelColor = (0.6274509803921569, 0.6274509803921569, 0.6274509803921569), limitStdDevs = False, lineWidth = 1.0, matrixColorMap = Greys, maxFalseAcceptRate = 99.999, maxFalseRejectionRate = 99.999, maximum4Type1 = 1e+99, maximum4Type3 = 1e+99, maxStdDev = 6.0, minimum4Type1 = -1e+99, minimum4Type3 = -1e+99, minNrScores4MatrixPlot = 3, minimumOpacityValue = 0.2, minStdDev = 0.01, noHistAnnot = False, normHist = True, nrAccPoints = 100, nrBins = 75, nrSamples4Probability = 500, opacity4Ellipses = 0.7, outputPath = output, printToFile = False, runningWindows = False, runningOSX = True, saveScores = True, scaleFactor = 100, screenResolution = 1600x1024, showAnnotationsAtStartup = False, showMeanScores = True, showCircularHistogram = True, det.showCllr = True, eer.showCllr = True, roc.showCllr = True, zoo.showCllr = True, showConfigInfo = True, showDiagonalInDet = True, showEdgeColor = True, roc.showEer = True, zoo.showEer = True, showHelperCircles = True, showKernelInHist = True, showMatrixLabels = True, showMetaInHist = True, det.showMinCllr = True, eer.showMinCllr = True, eer.showCounts = True, det.showCounts = True, roc.showCounts = True, tippet.showCounts = True, roc.showMinCllr = True, zoo.showMinCllr = True, showNrTargetsAndNonTargets = True, showReference = True, showSingleValueAsUnitValue = False, showStdev = True, showTextAtReferenceAtStartup = False, showUnitDataPoint = True, spacing = 0.02, useColorsForQuartileRanges = True, useOpacityForBigEllipses = False, xHeight = 0.2, yagerStyle = True, yWidth = 0.2, zBottom = 0.05, zHeight = 0.63, zLeft = 0.05, zWidth = 0.65

This will show the settings read from the file 'bioplot.cfg'. ::

    Ignoring all command line parameters except -s
    Config info as read from 'bioplot.cfg':
    alexanderStyle = True, alwaysSave = True, allowDups = False, alpha4References = 1.0, alpha4UnitCircles = 0.5, animalColors = True,
    annotateEllipsesInQuartiles = False, boutenStyle = True, combineMatrices = True, debug = False, dimmingFactor = 0.8, interconnectMetaValues = True,
    etc. etc.

If you do not want to see the list of settings each time bioplot is run, set ::

    [cfg]
    showConfigInfo = False

[accuracy]
----------
Number of points the accuracy is calculated for. ::

    nrPoints = 100

[cfg]
-----
Always save the target and non target scores, even if the files already exist. ::

    alwaysSave = True

'colorMap' is deprecated; have a look at [metacolors].

Set debug flag to True: will print a lot of info which might be of use when trying to debug the code. ::

 debug = False

Show config info at start of program on command line. ::

 showConfigInfo = True

Path to dir where results and plots are stored. ::

 outputPath = output

In stead of plotting on screen you can send plots to file.
The name of the file will be <exp_name>_<plot_type>_plot.png
Set printToFile to True to plot to file (default = False). ::

    printToFile = False

The height of the plot in inches. ::

    printToFileHeight = 10

The width of the plot in inches. ::

    printToFileWidth = 15

Are we running on OSX or not?
The Labels by default show black text on a yellow background.
The yellow background may be too large for the text.
If so, set runningOSX to True, this will change the yellow
background into a grey one and make the background fit the text in size. ::

    runningOSX = False

Are we running on Microsoft Windows or not?
The Labels by default show black text on a yellow background.
The yellow background may be too large for the text.
If so, set runningWindows to True, this will change the yellow
background into a grey one and make the background fit the text in size. ::

    runningWindows = False

Save all scores to text file separated in target and non target scores per meta value. ::

    saveScores = True

[data]
------
If set to True 'allowDups' allows for both scores in a symmetric trial to be used.
This means that the score of P vs Q and the score of Q vs P is used.
Otherwise only the first encountered in the raw scores is used. ::

    allowDups = False

Minimum value we expect for a score in type3 data. ::

    minimum4Type3 = -1.0E+99

Maximum value we expect for a score in type3 data. ::

    maximum4Type3 = 1.0E+99

Minimum value we expect for a score in type1 data. ::

    minimum4Type1 = -1.0E+99

Maximum value we expect for a score in type1 data. ::

    maximum4Type1 = 1.0E+99

[det]
-----
Show Cllr value(s). ::

 showCllr = True

Show minimum Cllr value(s). ::

 showMinCllr = True

Show Eer value(s).
Note, the EER is calculated as the point in a cumulative score plot where the line showing the target scores crosses the line for the non target scores.
The data points nearest to the crossing point are used and the crossing point is computed via interpolation. ::

 showEer = True

Set the upper limits for the False Accept Rate in %.
Choose from 0.001, 0.002, 0.005, 0.01, 0.02, 0.05, 0.1, 0.2, 0.5, 1, 2, 5, 10, 20, 40, 60, 80, 90, 95, 98, 99,
99.5, 99.8, 99.9, 99.95, 99.98, 99.99, 99.995, 99.998, 99.999 ::

 maxFalseAcceptRate = 60

Set the upper limits for the False Rejection Rate in %.
Choose from 0.001, 0.002, 0.005, 0.01, 0.02, 0.05, 0.1, 0.2, 0.5, 1, 2, 5, 10, 20, 40, 60, 80, 90, 95, 98, 99,
99.5, 99.8, 99.9, 99.95, 99.98, 99.99, 99.995, 99.998, 99.999 ::

 maxFalseRejectionRate = 60

[eer]
-----
Show Cllr value(s) in the plot.::

 showCllr = True

Show minimum Cllr value(s) in the plot. ::

 showMinCllr = True

[histogram]
-----------
Number of bins in the histogram.
Either specify a number or rice, sqrt or sturges.
See https://en.wikipedia.org/wiki/Histogram#Number_of_bins_and_width ::

 nrBins = 75

Normalize histogram. ::

 normHist = True

Show meta data values in histogram. ::

 showMetaInHist = True

Show kernel in histogram (if true, meta data values are disregarded). ::

 showKernelInHist = True

[layout]
--------
The layout is determined by these variables:

| bottom_h = left_h = zleft + zwidth + spacing
| The rectangle containing the zooplot: [zleft, zbottom, zwidth, zheight]
| The rectangle containing the histogram of target scores: [zleft, bottom_h, zwidth, xheight]
| The rectangle containing the histogram of non target scores: [left_h, zbottom, ywidth, zheight]

Do not change them unless you are certain what they are for.

Left bottom x-position of zoo plot in boutenZoo style layout. ::

  zLeft = 0.05

Width of zoo plot. ::

  zWidth = 0.65

Left bottom y-position of zoo plot in boutenZoo style layout. ::

  zBottom = 0.05

Height of zoo plot in boutenZoo style layout. ::

  zHeight = 0.63

Height of top histogram in boutenZoo style layout. ::

  xHeight = 0.2

Width of right hand side histogram in boutenZoo style layout. ::

  yWidth = 0.2

Resolution of screen used width x height, eg 1280x1024 ::

  screenResolution = 1600x1024

Spacing between zoo plot and left side of histograms in boutenZoo style layout. ::

  spacing = 0.02

Use same scale for vertical axis as for horizontal axis. ::

  showEqualAxes = False

[matrix]
--------
Not working at the moment:
In the cross identification plot, we want at least
this number of scores per label, otherwise skip
the label. ::

    minNrScores4MatrixPlot = 25

Color map of the plot. Choose a colormap: Greys, Spectral, gist_ncar, hsv, gist_rainbow or prism ::

    matrixColorMap = Greys

When set to True: combine matrices (if there are multiple
because of different meta values) in a square or oblong matrix,
otherwise make a horizontal bar or vertical column of matrices. ::

    combineMatrices = True

Show labels at tick marks. ::

    showMatrixLabels = True

Rotate xtick labels at a degree. ::

    labelAngle = 70

[metacolors]
------------
Different colors make it possible to combine multiple data sets in one plot.
Note: don't use white or some very light colour as the plot's
canvas is white and you would not see much of a label then.
From a perceptual point you should avoide pure Blue
in combination with other colors as the human eye does not focus
blue light in the same way as the other colours because of chromatic aberation
when viewing multiple colours at the same time. Blue will be less visible because
it will not be in focus when other colours are near it.
The meta data values are sorted alphabetically.
The colors are used in the sequence they are listed here.
Note that the labels are of no consequence! They are there for your convenience.
Values should be in R,G,B format specifying integer values
or hexadecimal values (6 digits). Have a look at http://colorbrewer2.org. I'm certain
you will get inspired to use some nice colours in the plots.
Alternatively you can search for color values on the web using 'html colors' as the search string
and you will find various lists and examples. ::

    Orangy = 255,125,10
    someSortOfPink = 255,54,160
    IWouldCallThisBlueIsh = 3399FF
    OneOf50ShadesOfGrey = 10,5,8
    rustLike = 96,17,0
    someWhatBlue = 1414FF
    definatelyGreen = 0,255,0
    definatelyRed = 255,0,0

[probability]
-------------
Number of threshold values used to calculate P(defense)
and P(prosecution) from target and non target scores
per meta value. ::

    nrSamples4Probability = 500

[roc]
-----
Show Cllr value(s) in the roc plot. ::

    showCllr = True

Show minimum Cllr value(s) in the roc plot. ::

    showMinCllr = True

Show EER value(s) in the roc plot. ::

    showEer = True

[zoo]
-----
Show ellipses at position of data points representing standard deviation of target and non target scores
as published by Alexander et al. @ IAFPA conference Zurich, Switzerland, 2014. ::

  alexanderStyle = True

Transparency value for inner most reference circle. ::

  alpha4References = 1.0

Transparency value for unit circles. ::

  alpha4UnitCircles = 0.5

Show DOVES CHAMELEONS and other labels in different colors.
When set to single, all will be grey. ::

  animalColors = multi


Show labels for quartile data points at startup. ::

  annotateEllipsesInQuartiles = False

Add target and non target score histogram to zoo plot. ::

  boutenStyle = True

If we add labels to the command line, we dimm al the none matching points and
ellipses by this factor thus making the given labels more prominent. ::

  dimmingFactor = 0.8

Draw lines between labels with opposing metadata values (only if alexanderStyle = True). ::

 interconnectMetaValues = True

Color used for label in zoo plot.
Note: don't use white or some very light colour as the plot's
canvas is white and you would not see much of a label then.
Values should be in R,G,B format using integer values (e.g. 105, 225, 5)
or hexadecimal values (e.g. 0FA022). ::

  labelColor = A0A0A0

Limit the std dev values of average target and average non target scores. ::

  limitStdDevs = True

Width of lines interconnecting ellipses in zoo plot. ::

  lineWidth = 1.0

Maximum normalized standard deviation allowed for an ellipse in the zoo plot.
Values any higher are limited to this number of normalized standard deviations. ::

  maxStdDev = 6.0

Opacity can be varied from small to large ellipses.
The opacity values are normalised using the surface area of the ellipse.
If it gets too small, the ellipses will not be visible anymore.
Therefore it is limited to this value. ::

  minimumOpacityValue = 0.2

Minimum normalized standard deviation allowed for an ellipse in the zoo plot.
Values any lower are limited to this number of normalized standard deviations.
minStDev may not exceed 1.0. ::

  minStdDev = 0.01

Histogram annotation on x-axis. When True will prevent the use of x-axis labels in the histograms added to the zoo plot.
Tricky ... This parameter implies a double negative. ::

  noHistAnnot = False

Opacity of ellipses if useOpacityForBigEllipses is set to False. ::

  opacity4Ellipses = 0.7

Scale ellipses to screen resolution. 100 should be good for 1600x1024 until 1280x1024.
Make it smaller if you want bigger ellipses. ::

    scaleFactor = 100

Show all annotations when starting program; one click on the figure will make them disappear.
Will only work if interconnectMetaValues is set to False. ::

  showAnnotationsAtStartup = False

Show average target match score and non match score in popup when data point is clicked. ::

  showAverageScores = True

Show histogram of shift of points depending on meta data values. ::

  showCircularHistogram = True

Show Cllr values in legend of relevant plots. ::

  showCllr = True

Show edge of ellipse in same color as ellipse (otherwise black). ::

  showEdgeColor = False

Show circles around unit ellipse that can be used to resize the plot so that the unit circle
will be shown as a circle. This will make it easier to interpret the std values for average target vs
average non target data points. ::

  showHelperCircles = True

Show min Cllr values in legend of relevant plots. ::

  showMinCllr = True

Show nr of target and nr of non target scores for a data point in zoo plot. ::

  showNrTargetsAndNonTargets = True

Show reference ellipses or not. ::

  showReference = True

In the data set there may be subjects with limited scores available. In case there is only one target score,
(or one non target score) one can not plot an ellipse for the corresponding axis.
In this case bioplot provides the option to either set the normalized std dev for this subject to the
minimum value which will result in a flat line for that dimension of the ellipse
or assume this subject is similar to other subjects and set the normalized std dev for this subject to the
unit value derived from the other subject target and non target scores. The default is to use the minimum value allowed. ::

  showSingleValueAsUnitValue = False

Show std dev values of data points when clicked. ::

  showStdDev = True

Do not show text with reference ellipses. ::

  showTextAtReferenceAtStartup = False

Show mean of average target and non target points as a black dot. ::

  showUnitDataPoint = True

Give distinct colors to data points within quartile ranges. This is only done when the
metadata field contains only one distinct value. ::

  useColorsForQuartileRanges = True

Big ellipses may overshadow smaller ones at the same position.
Using opacity makes the smaller ones visible again. ::

  useOpacityForBigEllipses = False

Use vertical axis as proposed by Yager et al.
When set to False the y-axis will be inversed. ::

  yagerStyle = True

