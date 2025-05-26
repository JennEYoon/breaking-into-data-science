# Project Plan  

Author: Jennifer E Yoon  
Date:   May 26, 2025  

### Plan of action:  

#### Deliverables:  
 * Write out presentation draft & slides (3-5). 2 minutes.
   * Get plots, Geron image ResNet+SE, CNN architecture, simple diagram.
   * Signup for paid plan, Claud Code or OpenAI? 
 * one Jupyter notebook
   * plots
   * text explanation of model architecture
   * description of Jason's ECG device, signal output sample & processing information
   * inference using Jason's device
  * dataset - link to tiny pre-processed data, in .csv form?  
  
#### Data files, refactoring header, data, many files into 2 outputs   
 * Use example from forked repo, data exploratory notebook.  
 * work with g1 folder first, 1000 files (12 signals x 10 sec * 500 samples/sec)
   and 1000 header text files. 
 * Do exploratory data analysis for class project on this folder.
   Only matter header data, count, abnormal diagnostic distribution.
   Reformat header information into a database, or Pandas DataFrame, save as csv format.
   > ***forked repo*** shows how to process header text into rows with file names, diagnostic info, age, sex info.
   > sample nb reads header file into dataframe, return 1 row per file, then saves multiple rows into one .csv out file.
   > do same with my method. Find baseline zero centering method.
   > "main" branch has code for ResNet+SE model. Trained all many different hospital datasets. Some were used only for testing.

#### contents, plots, notebook      
 * Signal data, read into and do a few charts. Show splitting?  Maybe just one.
   Some plotting, shoiwng 12 signals, how split into 1 heart beat x 12 channels.
 * Do CNN, after converting signal data into peak centered samples, .csv format, just this folder. Class is binary, and 4 or 6.  Map diagnostic classes into larger groups before training.  Try with all 24 classes once. 20-50 epochs final model.
 * Do ResNet without SE, Just this one folder first.  Do with binary classes first, then 4 or 6. Try 24 classes if I have time. Use 20 epochs.
 * Do ResNet with SE, try to read code in repo provided. Get help from AI.
   Still use just this folder.
 * Convert Jason's ECG data, do prediction/inference, just 2 classes.
   Can't run other classes because don't have data for different classes.
   Try augmenting some hospital data abnormal to simulate Areteus device output with abnormal patient somehow? Is this possible? Do need at least 1 source. Lou had a heart attach and surgery, his heart may show trace. Get sample?
  * Show picture of signals side-by-side, normal heart, Areteus and hospital recording.
  * Future steps.
     - before SciPy, try to get Areteus samples from abnormal heart patients.
     - build Transformers + RNN model, do cross-hospital dataset test.
     - do binary classification test on original ECGTransform model, ptb-xl full data.  With saved weights, apply to Areteus data (need normal and abnormal heartbeats).
     - verify input to original ECGTransform is 1x5000 single channel conv first layer. NOT 12-channel conv layer. Verify that relationship between 12-signals were broken and each signal was fed as an independent heart beat sample into the original model.
   
       


