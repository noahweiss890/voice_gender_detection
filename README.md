# gender-detection

As part of the [VOICE Summit](https://www.voicesummit.ai/), I am hosting a machine learning workshop on using the [Voicebook](https://github.com/jim-schwoebel/voicebook). In this workshop, I overview how to train a machine learning model to detect males from females from audio files. 

![](https://media.giphy.com/media/l0HlVq3nJvhSZiZEs/giphy.gif)

## The dataset

I downloaded all the files from [VoxCeleb2](http://www.robots.ox.ac.uk/~vgg/data/voxceleb/). After this, I cleaned the data to separate all the males from the females. I took one voice file at random for all the males and females so as to provide unique files.

![](https://github.com/jim-schwoebel/gender-detection/blob/master/data/Screen%20Shot%202019-07-22%20at%2011.16.14%20AM.png)

You can download the prepared dataset from [this link](https://drive.google.com/file/d/1HRbWocxwClGy9Fj1MQeugpR4vOaL9ebO/view).

## Featurization techniques

Intuitively, we know that most of the features that matter for separating out genders are mostly audio-related features like the fundamental frequency, MFCC coeffiicents, and formant frequencies. 

To simplify things, we can just featurize the files with the train_audioclassify.py script. I slighly modified this script to include being able to take in .M4A files and converting them to .WAV files.

This featurizes all the files appropriately into .JSON files like this:

```
{"features": [-353.90257942328554, 58.01672170639758, -703.2908063668561, -244.59664968903266, 120.77438799548838, 48.587638379552686, 0.0, 206.23937949197023, -17.614903082924762, 21.896880584719494, -93.53524512304182, 39.25891412027272, 71.5585736549912, 31.216641866853976, -4.1097497409468655, 147.80726459654613, -11.212912690856928, 26.241167154558216, -93.3273860041447, 33.39406296150048, 17.385199406906743, 17.812256829651783, -15.775957864593206, 71.2976899178332, -27.475327059655772, 17.29486585997999, -72.30450274808385, 16.555004086550632, 1.3154971178660386, 15.045541210536745, -34.91050791010009, 36.23435893500907, -10.736291647533783, 11.850996840148898, -38.55204075924968, 17.08622970202298, -7.794566613463251, 9.080422143454681, -32.85545573295984, 14.14811618776311, -10.1821346272071, 9.596484081862144, -42.976800137609224, 18.983509328321023, -10.085169587133, 7.838356955314714, -29.87348386201144, 15.39133575524436, 2.21927290207588, 6.888356028816847, -19.172128831473927, 18.15741693999623, -0.9291675352603528, 12.576850016655293, -37.051447993039474, 32.92362919622146, 0.10573689916014054, 10.789639202489477, -23.490694209053974, 24.671154779939425, -0.01629452157074945, 4.433766495443947, -11.142467331094984, 15.493827623920136, 0.17573108461133594, 6.427849955456987, -16.826745664570108, 19.093468482334636, 0.4173772558279777, 5.551845120120025, -13.96684516782555, 14.647753711947907, -0.13604156159188882, 3.838525192356469, -10.242221290651118, 9.865500478056386, 0.18312786648656101, 3.713931812887859, -8.746542201847214, 7.039678136997143, -0.1156850991593573, 3.331736740379702, -8.073791330947259, 8.742059331786745, 0.1943999961523158, 1.928274091002802, -6.289087093770005, 4.253015942505109, -0.15227882868669954, 1.7794453105311643, -4.985202596317516, 4.458126480445773, -0.01990872747521754, 1.7621594175996373, -5.507148800360761, 5.600782235826579, 0.031014894536071806, 1.1640592421749514, -2.728100820895949, 3.518347326841714, -0.05704584862225418, 1.3921398794420592, -3.9409657702177654, 3.489564362897586, -40.151813144983024, 5.950517472992894, -49.34503450029317, -28.683742793608165, 15.727627542142779, 7.797730402032888, -1.0491314918340835, 25.77992243649628, -1.8481648389201435, 2.797469322091307, -6.725810547443524, 3.2079518282940693, 6.806005243735187, 3.7964095386621173, 0.8864980798360538, 14.78516612300923, -2.7535395662737647, 3.4489392434551163, -7.405200391272226, 3.635880010797687, 2.1522411143011846, 1.8879916910378791, -0.07112269107952354, 6.30224475627656, -4.675803858738777, 2.532142530211178, -9.038062843510481, 0.0420118619989896, -0.30375097359594255, 2.9110433901249833, -4.1552391436218965, 4.529294866876134, -2.0540693105317085, 1.3461096219830693, -3.9712222862092643, 0.6630461376529606, -0.9157642418498797, 1.0097019614734404, -2.3922264545952787, 0.7673701453082771, -1.7796014228347945, 1.4539519485762857, -5.372100017201153, 0.43555065900440093, -1.8461844818049344, 1.041907648535014, -3.8606951077969747, 0.34998386129101644, -0.107616150299151, 1.1046699346585973, -2.396516103934241, 1.5096538177891154, 0.6347088123470858, 1.0892073311101835, -1.2553296114221593, 2.5230047469160866, 0.1722624017918903, 1.8518190235596568, -2.398730145651318, 3.083894347492428, 0.01301137686073959, 0.5349383203841249, -0.9954767461611344, 0.7837855794519846, 0.46160195048517966, 0.7040488660965134, -1.0060353980563808, 1.2298063908674715, 0.2543028665321045, 0.5518685910277583, -0.34013348915424313, 1.4529802275102828, -0.13012888884825968, 0.31820989899446706, -0.7697971157550454, 0.24009171929379497, 0.14263686001849904, 0.5712258640566474, -1.015970774725115, 0.7810490874346672, -0.2711011653441329, 0.3916818703065981, -1.0092239163684074, 0.21513224077628454, 0.14348795775826292, 0.23612641254819336, -0.13031067424234943, 0.5316269928131386, -0.0992375489967987, 0.21747840902867793, -0.43557271818530324, 0.1418337399826225, -0.1344329753837571, 0.22892381923790125, -0.6883936000450951, 0.13727461110098693, -0.06237816425870175, 0.223239850355424, -0.33660386623955496, 0.43979341585521425, -0.023783173746338017, 0.2778740777883613, -0.4926207212772207, 0.43619554536219823]}
```
These .JSON files have the labels 

```
labels = ['mfcc1_mean_(0.02 second window)', 'mfcc1_std_(0.02 second window)', 'mfcc1_max_(0.02 second window)', 'mfcc1_min_(0.02 second window)', 
		'mfcc2_mean_(0.02 second window)', 'mfcc2_std_(0.02 second window)', 'mfcc2_max_(0.02 second window)', 'mfcc2_min_(0.02 second window)', 
		'mfcc3_mean_(0.02 second window)', 'mfcc3_std_(0.02 second window)', 'mfcc3_max_(0.02 second window)', 'mfcc3_min_(0.02 second window)', 
		'mfcc4_mean_(0.02 second window)', 'mfcc4_std_(0.02 second window)', 'mfcc4_max_(0.02 second window)', 'mfcc4_min_(0.02 second window)', 
		'mfcc5_mean_(0.02 second window)', 'mfcc5_std_(0.02 second window)', 'mfcc5_max_(0.02 second window)', 'mfcc5_min_(0.02 second window)', 
		'mfcc6_mean_(0.02 second window)', 'mfcc6_std_(0.02 second window)', 'mfcc6_max_(0.02 second window)', 'mfcc6_min_(0.02 second window)', 
		'mfcc7_mean_(0.02 second window)', 'mfcc7_std_(0.02 second window)', 'mfcc7_max_(0.02 second window)', 'mfcc7_min_(0.02 second window)', 
		'mfcc8_mean_(0.02 second window)', 'mfcc8_std_(0.02 second window)', 'mfcc8_max_(0.02 second window)', 'mfcc8_min_(0.02 second window)', 
		'mfcc9_mean_(0.02 second window)', 'mfcc9_std_(0.02 second window)', 'mfcc9_max_(0.02 second window)', 'mfcc9_min_(0.02 second window)', 
		'mfcc10_mean_(0.02 second window)', 'mfcc10_std_(0.02 second window)', 'mfcc10_max_(0.02 second window)', 'mfcc10_min_(0.02 second window)', 
		'mfcc11_mean_(0.02 second window)', 'mfcc11_std_(0.02 second window)', 'mfcc11_max_(0.02 second window)', 'mfcc11_min_(0.02 second window)', 
		'mfcc12_mean_(0.02 second window)', 'mfcc12_std_(0.02 second window)', 'mfcc12_max_(0.02 second window)', 'mfcc12_min_(0.02 second window)', 
		'mfcc13_mean_(0.02 second window)', 'mfcc13_std_(0.02 second window)', 'mfcc13_max_(0.02 second window)', 'mfcc13_min_(0.02 second window)', 
		'mfccdelta1_mean_(0.02 second window)', 'mfccdelta1_std_(0.02 second window)', 'mfccdelta1_max_(0.02 second window)', 'mfccdelta1_min_(0.02 second window)', 
		'mfccdelta2_mean_(0.02 second window)', 'mfccdelta2_std_(0.02 second window)', 'mfccdelta2_max_(0.02 second window)', 'mfccdelta2_min_(0.02 second window)', 
		'mfccdelta3_mean_(0.02 second window)', 'mfccdelta3_std_(0.02 second window)', 'mfccdelta3_max_(0.02 second window)', 'mfccdelta3_min_(0.02 second window)', 
		'mfccdelta4_mean_(0.02 second window)', 'mfccdelta4_std_(0.02 second window)', 'mfccdelta4_max_(0.02 second window)', 'mfccdelta4_min_(0.02 second window)', 
		'mfccdelta5_mean_(0.02 second window)', 'mfccdelta5_std_(0.02 second window)', 'mfccdelta5_max_(0.02 second window)', 'mfccdelta5_min_(0.02 second window)', 
		'mfccdelta6_mean_(0.02 second window)', 'mfccdelta6_std_(0.02 second window)', 'mfccdelta6_max_(0.02 second window)', 'mfccdelta6_min_(0.02 second window)', 
		'mfccdelta7_mean_(0.02 second window)', 'mfccdelta7_std_(0.02 second window)', 'mfccdelta7_max_(0.02 second window)', 'mfccdelta7_min_(0.02 second window)', 
		'mfccdelta8_mean_(0.02 second window)', 'mfccdelta8_std_(0.02 second window)', 'mfccdelta8_max_(0.02 second window)', 'mfccdelta8_min_(0.02 second window)', 
		'mfccdelta9_mean_(0.02 second window)', 'mfccdelta9_std_(0.02 second window)', 'mfccdelta9_max_(0.02 second window)', 'mfccdelta9_min_(0.02 second window)', 
		'mfccdelta10_mean_(0.02 second window)', 'mfccdelta10_std_(0.02 second window)', 'mfccdelta10_max_(0.02 second window)', 'mfccdelta10_min_(0.02 second window)', 
		'mfccdelta11_mean_(0.02 second window)', 'mfccdelta11_std_(0.02 second window)', 'mfccdelta11_max_(0.02 second window)', 'mfccdelta11_min_(0.02 second window)', 
		'mfccdelta12_mean_(0.02 second window)', 'mfccdelta12_std_(0.02 second window)', 'mfccdelta12_max_(0.02 second window)', 'mfccdelta12_min_(0.02 second window)', 
		'mfccdelta13_mean_(0.02 second window)', 'mfccdelta13_std_(0.02 second window)', 'mfccdelta13_max_(0.02 second window)', 'mfccdelta13_min_(0.02 second window)', 
		'mfcc1_mean_(0.50 second window)', 'mfcc1_std_(0.50 second window)', 'mfcc1_max_(0.50 second window)', 'mfcc1_min_(0.50 second window)', 
		'mfcc2_mean_(0.50 second window)', 'mfcc2_std_(0.50 second window)', 'mfcc2_max_(0.50 second window)', 'mfcc2_min_(0.50 second window)', 
		'mfcc3_mean_(0.50 second window)', 'mfcc3_std_(0.50 second window)', 'mfcc3_max_(0.50 second window)', 'mfcc3_min_(0.50 second window)', 
		'mfcc4_mean_(0.50 second window)', 'mfcc4_std_(0.50 second window)', 'mfcc4_max_(0.50 second window)', 'mfcc4_min_(0.50 second window)', 
		'mfcc5_mean_(0.50 second window)', 'mfcc5_std_(0.50 second window)', 'mfcc5_max_(0.50 second window)', 'mfcc5_min_(0.50 second window)', 
		'mfcc6_mean_(0.50 second window)', 'mfcc6_std_(0.50 second window)', 'mfcc6_max_(0.50 second window)', 'mfcc6_min_(0.50 second window)', 
		'mfcc7_mean_(0.50 second window)', 'mfcc7_std_(0.50 second window)', 'mfcc7_max_(0.50 second window)', 'mfcc7_min_(0.50 second window)', 
		'mfcc8_mean_(0.50 second window)', 'mfcc8_std_(0.50 second window)', 'mfcc8_max_(0.50 second window)', 'mfcc8_min_(0.50 second window)', 
		'mfcc9_mean_(0.50 second window)', 'mfcc9_std_(0.50 second window)', 'mfcc9_max_(0.50 second window)', 'mfcc9_min_(0.50 second window)', 
		'mfcc10_mean_(0.50 second window)', 'mfcc10_std_(0.50 second window)', 'mfcc10_max_(0.50 second window)', 'mfcc10_min_(0.50 second window)', 
		'mfcc11_mean_(0.50 second window)', 'mfcc11_std_(0.50 second window)', 'mfcc11_max_(0.50 second window)', 'mfcc11_min_(0.50 second window)', 
		'mfcc12_mean_(0.50 second window)', 'mfcc12_std_(0.50 second window)', 'mfcc12_max_(0.50 second window)', 'mfcc12_min_(0.50 second window)', 
		'mfcc13_mean_(0.50 second window)', 'mfcc13_std_(0.50 second window)', 'mfcc13_max_(0.50 second window)', 'mfcc13_min_(0.50 second window)', 
		'mfccdelta1_mean_(0.50 second window)', 'mfccdelta1_std_(0.50 second window)', 'mfccdelta1_max_(0.50 second window)', 'mfccdelta1_min_(0.50 second window)', 
		'mfccdelta2_mean_(0.50 second window)', 'mfccdelta2_std_(0.50 second window)', 'mfccdelta2_max_(0.50 second window)', 'mfccdelta2_min_(0.50 second window)', 
		'mfccdelta3_mean_(0.50 second window)', 'mfccdelta3_std_(0.50 second window)', 'mfccdelta3_max_(0.50 second window)', 'mfccdelta3_min_(0.50 second window)', 
		'mfccdelta4_mean_(0.50 second window)', 'mfccdelta4_std_(0.50 second window)', 'mfccdelta4_max_(0.50 second window)', 'mfccdelta4_min_(0.50 second window)', 
		'mfccdelta5_mean_(0.50 second window)', 'mfccdelta5_std_(0.50 second window)', 'mfccdelta5_max_(0.50 second window)', 'mfccdelta5_min_(0.50 second window)', 
		'mfccdelta6_mean_(0.50 second window)', 'mfccdelta6_std_(0.50 second window)', 'mfccdelta6_max_(0.50 second window)', 'mfccdelta6_min_(0.50 second window)', 
		'mfccdelta7_mean_(0.50 second window)', 'mfccdelta7_std_(0.50 second window)', 'mfccdelta7_max_(0.50 second window)', 'mfccdelta7_min_(0.50 second window)', 
		'mfccdelta8_mean_(0.50 second window)', 'mfccdelta8_std_(0.50 second window)', 'mfccdelta8_max_(0.50 second window)', 'mfccdelta8_min_(0.50 second window)', 
		'mfccdelta9_mean_(0.50 second window)', 'mfccdelta9_std_(0.50 second window)', 'mfccdelta9_max_(0.50 second window)', 'mfccdelta9_min_(0.50 second window)', 
		'mfccdelta10_mean_(0.50 second window)', 'mfccdelta10_std_(0.50 second window)', 'mfccdelta10_max_(0.50 second window)', 'mfccdelta10_min_(0.50 second window)', 
		'mfccdelta11_mean_(0.50 second window)', 'mfccdelta11_std_(0.50 second window)', 'mfccdelta11_max_(0.50 second window)', 'mfccdelta11_min_(0.50 second window)', 
		'mfccdelta12_mean_(0.50 second window)', 'mfccdelta12_std_(0.50 second window)', 'mfccdelta12_max_(0.50 second window)', 'mfccdelta12_min_(0.50 second window)', 
```

## Modeling techniques 

I used the train_audioTPOT.py script to train the model.

## Making model predictions 

All you need to do to make a model prediction is to provide an audio file from the command line. Note that the audio file must be a .WAV file in order for it to make a proper prediction.

```
predict.py test.wav
```

This will look for the file test.wav in the current directory, featurize the file, and then make a model prediction appropriately. If you'd like to save this model prediction as .JSON, feel free to pass through another argument at the end.

```
predict.py test.wav yes
```

This will featurize the file test.wav and save the model prediction in 'test.json.' 

## References
* [prepared dataset](https://drive.google.com/file/d/1HRbWocxwClGy9Fj1MQeugpR4vOaL9ebO/view)
* [VOICE Summit](https://www.voicesummit.ai/)
* [VoxCeleb2](http://www.robots.ox.ac.uk/~vgg/data/voxceleb/)
