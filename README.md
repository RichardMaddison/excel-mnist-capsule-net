# excel-mnist-capsule-net
IMPORTANT NOTICE	
	This spreadsheet is a MNIST classifier using a Capsule Net. It is built in Excel MSO 365 64 bit. Whilst I’ve have made every effort to remove coding errors the model will, inevitably contain some and should not be relied upon under an assumption of completeness.
	This spreadsheet has been provided to the Recipient / Current user under the Creative Commons Attribution-NonCommercial 4.0 International Licence the details of which can be found here: 
	https://creativecommons.org/licenses/by-nc/4.0/legalcode
	This model was developed by RICHARD MADDISON. It contains MNIST data gathered from LeCun et al. (1999): The MNIST Dataset of Handwritten Digits (Images). The MNIST dataset of handwritten digits, has a training set of 60,000 examples, and a test set of 10,000 examples. It is a subset of a larger set available from NIST. The digits have been size-normalized and centred in a fixed-size image. See 
	http://yann.lecun.com/exdb/mnist
	
ABOUT RICHARD MADDISON	
	I build models for a living and have been doing this for a couple of decades. I’m good at excel, have a lot of direct experience in the energy sector and consulting experience in most others. If you have a commercial modelling challenge you want help with please contact me on RichardMaddison@gmail.com, you can see more on my LinkedIn profile https://www.linkedin.com/in/richard-maddison-332158/
	I have been looking at Neural Networks for a while and have a blog on these – primarily my Excel base models on www.richardmaddison.com. You can also reach me on twitter https://twitter.com/RichardMaddison/media, GitHub https://github.com/RichardMaddison and YouTube https://www.youtube.com/channel/UC44Q4IXVrU6qUtezNU9X_Uw?view_as=subscriber

ABOUT THE MODEL	
	The model is controlled from the Dash tab. Tab "1" represents the full model.  The Con tab holds a few display and control type constants. Train and Test hold the data from Yan LeCun.

Controls:	
	Test: This macro will run cases from the Test tab through the model. Using only the forward model. The number of iterations is set in Target Iterations cell and counted in Counter Iterations. Press reset to zero these out.
	Learn: This macro runs cases from the Train tab through the model. As with Test, it will run up to the number specified in the Target Iterations Cell (minus the number in Counter). Use Momentum  & RMS Prop optimisation (collectively Adam) for faster learning 
	Reset: will Clear the charts and counters but retain the learned Parameters.
	Initialisation: will Initialise all input parameters.
	Load: Loads saved Parameters from the Best Parameters Stores on tab 1.
	Load Keras : Loads Parameters that I trained in Keras.
	Save: Overwrites the Parameters in the Best Parameters Stores on Tab 1.
	Axis: Ugly macro to set the scale of the Loss and Precision Charts to match the interations count
	Reconstructed Digit: Here you can explore the 8 dimensions of digit capsules. Use the Select Dimension drop down to cycle through a given dimension. You can use the spinner for deeper exploration or the Macro button to cycle through all.
	
Inputs:	
	Target Iterations: how many mini batches the model will run for Test or Learn
	Learning Rate: 0.01 works well
	BetaM: The Momentum Beta 0.9 works well for roughly a 10 batch look back on this exponentially weighted decay
	BetaR: The RMS Prop Beta 0.99 for a long look back, think of this as about 100 meaningful previous iterations.
	Epsilon: a tiny constant to stop the RMS Dividing by zero.
	Scale: the X axis scaling of charts – set this then press Axis.
	Step: How often a dot is recorded on the X-Plots.  These Plots have only 1000 points to if you run 10,000 iterations set this to 10 in order to make full use of the chart. This will also determine the mean precision denominator for the top left chart.
	Run: Used with Find Best to see how many attempts the model made to beat the Best results in the Best Curve Tracking.
