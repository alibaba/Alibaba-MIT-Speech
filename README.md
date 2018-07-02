# Alibaba-MIT-Speech
This is a PATCH file with the DFSMN related codes and example scripts for LibriSpeech task.  

# Apply Patch

The patch is built based on [the Kaldi speech recognition toolkit](https://github.com/kaldi-asr/kaldi) with commit "04b1f7d6658bc035df93d53cb424edc127fab819". 

You can apply this patch to your own kaldi branch by using the following commands:
(*Instead of applying the PATCH file, one can also directly clone the project at "https://github.com/tramphero/kaldi"*)

##Take a look at what changes are in the patch

git apply --stat Alibaba_MIT_Speech_DFSMN.patch

##Test the patch before you actually apply it

git apply --check Alibaba_MIT_Speech_DFSMN.patch

##If you don’t get any errors, the patch can be applied cleanly.

git am --signoff < Alibaba_MIT_Speech_DFSMN.patch



# Run Example Scripts:

The training scripts and experimental results for the LibriSpeech task is available at kaldi/egs/librispeech/s5.

There are three DFSMN configurations with different model size: DFSMN_S, DFSMN_M, DFSMN_L. 

**********************************************************************************

#Training FSMN models on the cleaned-up data

#Three configurations of DFSMN with different model size: DFSMN_S, DFSMN_M, DFSMN_L

local/nnet/run_fsmn_ivector.sh DFSMN_S

local/nnet/run_fsmn_ivector.sh DFSMN_M

local/nnet/run_fsmn_ivector.sh DFSMN_L

**********************************************************************************

The DFSMN_S is a small DFSMN with six DFSMN-components while DFSMN_L is a large DFSMN consist of 10 DFSMN-components. 

For the 960-hours-setting, it takes about 2-3 days to train DFSMN_S only using one M40 GPU. 

And the detailed experimental results are listed in the RESULTS file.


