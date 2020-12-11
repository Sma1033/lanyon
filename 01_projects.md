---
layout: page
title: Projects
---

<a></a>

## Drum pattern generation using Self-Similarity Matrix   

#### The flow of generation
![Generation Flow](../pics/drum_system_diagram.jpg "Generation Flow")

In this project, a Variational Autoencoders (VAEs) based drum pattern generation model is built to generate symbolic drum patterns
given an accompaniment that consists of melodic sequences. A self-similarity matrix (SSM) is incorporated in the process for encapsulating structural information. The subjective listening test highlight the model’s capability of creating musically meaningful transitions on structural boundaries.

For more details, please check our ISMIR 2019 conference [paper](./paper/drum_generation_paper.pdf){:target="_blank"}, [poster](./paper/drum_generation_poster.pdf){:target="_blank"}, [slide](./paper/drum_generation_slide.pdf){:target="_blank"} and [GitHub](https://github.com/Sma1033/drum_generation_with_ssm/){:target="_blank"}. Audio samples are also available [here](https://sma1033.github.io/drum_generation_with_ssm/){:target="_blank"}. (may take a while to open)

<br>


--- 

## Real-time score following for enriched musical concert

This is a project collaborated with [Pacing Art Culture Education Foundation](http://www.pacing.com.tw/pacing/){:target="_blank"}. In this work, a low-latency, efficient real-time score following system is proposed to predict the score position of a given song in a live classical concert. The system is implemented with Parallel Dynamic Time Warping (PDTW) algorithm on a multi-core system. Its output (predicted current score position) is used to drive a visualization system to project pre-programmed animation effects on screen. For more details, please check our MMSP 2018 conference [paper](./paper/mmsp_pdtw_paper.pdf){:target="_blank"} and [poster](./paper/mmsp_pdtw_poster.pdf){:target="_blank"}.

### Concert flyer
<!--![Concert flyer](../pics/concert_flyer.jpg =536x381)-->
<img src="../pics/concert_flyer.jpg" alt="concert flyer" width="590" height="420"/>

### Concert video
<a href="http://www.youtube.com/watch?feature=player_embedded&v=2SRBgtO7_Ck" target="_blank"><img src="http://img.youtube.com/vi/2SRBgtO7_Ck/0.jpg" alt="IMAGE ALT TEXT HERE" width="424" height="270" border="1.5" /></a>

<br>


---

## Real-time beat tracking in audio signals
    
This is a project that utilizes off-line beat tracking package ([Madmom](https://github.com/CPJKU/madmom){:target="_blank"}) to perform the real-time beat tracking task for an live audio signal.

Madmom is a well known Music Information Retrieval (MIR) oriented python package that performs off-line beat tracking on music with state-of-the-art performance. However, It's downbeat tracking result is not stable in particular scenarios. For example, It usually confuses with the location of the first beat and the third beat in a standard 4/4 time signature music clip.

To tackle this issue, a voting mechanism is employed to improve the downbeat tracking result. First, the live music input is segmented into multiple overlapped clips. Then, the downbeat tracking result of clips are merged by a simple majority vote mechanism. The program utilizes multi-core computation power to retrieve the beat location of multiple music segments simultaneously. Although the idea sounds simple and brutal, surprisingly, It works nicely and reliably with live music input.

### Real-time beat tracking demo
<a href="http://www.youtube.com/watch?feature=player_embedded&v=hW_QP6qfwHQ" target="_blank"><img src="http://img.youtube.com/vi/hW_QP6qfwHQ/0.jpg" alt="IMAGE ALT TEXT HERE" width="424" height="270" border="1.5" /></a>

<!--[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/hW_QP6qfwHQ/0.jpg)](http://www.youtube.com/watch?v=hW_QP6qfwHQ)-->

<br>


---

## Interactive music interface

This is a project using microphone as input source to query the music clip in an audio database. If the similarity value between the input and the database audio clip is higher than a certain threshold, a pre-programmed audio file is played as the query response. The system can be used in scenarios such as automatic accompaniment, human-AI duet or AI orchestra.

Chroma-based Dynamic Time Warping (DTW) is an extremely reliable method to calculate the similarity between audio clips. However, It employs heavy computation for chroma feature conversion and alignment path calculation. In this project, a two-stage audio filtering system is proposed to speed up the process for real-world applications. In the first stage, roughly 90% of audio files in the database can be filtered out using the twelve-bin chroma vector hash value comparison. Then, an optimized DTW algorithm is applied to rank the remaining clips based on their similarity to the input source. The most similar clip in the database will be regarded as the retrieved result, and, the system will act accordingly by its similarity value. With such a two-stage filtering mechanism, the designed system is very responsive and can be adapted and applied to any live interactive performance.

### Interactive music interface demo
<a href="http://www.youtube.com/watch?feature=player_embedded&v=QbUSsDGDi_k" target="_blank"><img src="http://img.youtube.com/vi/QbUSsDGDi_k/0.jpg" alt="IMAGE ALT TEXT HERE" width="424" height="290" border="1.5" /></a>

<br>


--- 

## Create personalized instruments with your speech voice

#### The system diagram of "VOICE MIXER"
![Generation Flow](../pics/voice_mixer_diagram.jpg "VOICE MIXER")

VOICE MIXER is an automated audio processing system to create personalized musical instruments using the user’s speech voice. The processing flow is presented in the above figure. First, the user is asked to read and record a short English passage (roughly 100 words) randomly extracted from Wikipedia. Then, the recorded speech voice is processed and segmented into thirty-nine phonemes using a neural network model trained on the TIMIT speech dataset. After that, the extracted phonemes are mixed with pre-processed audio materials to create three different humanized musical instruments (lead vocal, bass and drum kit). Finally, the instruments are applied to database MIDI files for music playback. Since those extracted phonemes vary largely between users, everyone can create their own unique musical instruments with their voice.

Please check the Colab demo file [here](https://colab.research.google.com/drive/1tar4HcBUSKkBZFwSNTDONyAW0X_IVxIE){:target="_blank"}.

<br>


--- 


## Improve drum transcription with audio-2-MIDI dataset

#### Illustration of the proposed drum transcription system
![Generation Flow](../pics/adt_sys.jpg "ADT SYSTEM")

<br>

Automatic Drum Transcription (ADT) is a task that involves the isolation and identification of percussive events from audio signals. One of the major challenges in ADT research is the lack of large-scale labeled dataset featuring audio with polyphonic mixtures. To tackle this issue, we propose a semi-automatic way of compiling a labeled dataset using the audio-to-MIDI alignment technique. The resulting dataset consists of 1565 polyphonic mixtures of music with audio-aligned MIDI ground truth. To validate the quality and generality of this dataset, an ADT model based on Convolutional Neural Network (CNN) is trained and evaluated on several publicly available datasets. The evaluation results suggest that our proposed methodology compares favorably with state-of-the-art ADT systems. The result also implies the possibility of leveraging audio-to-MIDI alignment in creating datasets for a broader range of audio-related tasks. ([paper](./paper/drum_transcription_paper.pdf){:target="_blank"} submitted to ICASSP 2021)

The implemented drum transcription system is integrated in [Omnizart](https://github.com/Music-and-Culture-Technology-Lab/omnizart){:target="_blank"}.

<br>
<br>
<br>
--- 
Thanks for reading !


