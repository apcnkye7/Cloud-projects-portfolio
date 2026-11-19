<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Transcribe Audio Files with AI

**Project Link:** [View Project](https://nextwork.ai/projects/1542c25d-ea3b-5dc5-87fc-a77416aabb87)

**Author:** Gabby Hammond

---

![](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1542c25d-ea3b-5dc5-87fc-a77416aabb87_o2p3q4r1)

![](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1542c25d-ea3b-5dc5-87fc-a77416aabb87_o2p3q4r5)

## Introducing Today's Project!

In this project, I will demonstrate storing a video with Amazon S3,transcribe the video with Amazon Transcribe,write custom vocabularies to improve your transcription's accuracy,use custom filters to automatically remove unwanted words and transcribe my own voice as I talk live

### ✍️ What are we doing in this step?

In this step, I will create an S3 bucket and upload a video to the bucket.

### Tools and concepts

Services I used were Amazon Transcribe.Key concepts I learnt include  creating custom vocabulary, filter words, subtitles

### Project reflection

This project took me approximately an hour

I chose to do this project today because i am building a portfolio Something that would make learning with NextWork even better is more secret projects

## S3 and Transcribe

To set up for this project, I'm using an S3 bucket to store a video file because we will be using amazon Transcribe to transcribe a video file and since transcribe has no storage feature we use that of S3 The file I'm transcribing is a 1min video clip

### ✍️ What are we doing in this step?

In this step, I will create my first transcription with Amazon Transcribe and analyze the generated transcription.

![S3 and Transcribe](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1542c25d-ea3b-5dc5-87fc-a77416aabb87_k1l4m7n0)

## Run A Transcription Job

The steps to run a transcription job include naming the job, uploading the bucket,keeping the default configurations for the baseline. Overall, this process took me about 5 minutes

Amazon Transcribe uses model types to understand different types of speech. Use cases of model types include learning from the audio samples to recognize different accents, terminology, and background noise

You can customise a transcription further with subtitling, which adds  text files that display words spoken in a video and speaker partitioning, which helps  you to label different speakers in an audio recording i.e. who said what.

![Run A Transcription Job](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1542c25d-ea3b-5dc5-87fc-a77416aabb87_g0h1i2j3)

### ✍️ What are we doing in this step?

In this step, I will review the enhanced transcription

## Baseline Transcript Review

To start using Amazon Transcribe, I first ran a baseline transcription job, which means doing a first run without using any custom settings. This is because the baseline transcription gives you a starting point to compare to later when you add custom settings.

While reviewing the baseline transcript, I noticed a lot of punctuation mistakes.These happened because this is the baseline transcript.

### ✍️ What are we doing in this step?

In this step, I will create a custom vocabulary file,upload the file to your S3 bucket  and create a custom vocabulary in Amazon Transcribe

![Baseline Transcript Review](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1542c25d-ea3b-5dc5-87fc-a77416aabb87_s3t6u9v2)

## Custom Vocabulary

I can resolve transcription inaccuracies using a custom vocabulary, which  is a list of words or phrases that you want Amazon Transcribe to recognize. A custom vocabulary improves transcription accuracy by correcting the words you specify

### ✍️ What are we doing in this step?

In this step, I will create a vocabulary filter file,create a vocabulary filter in Amazon Transcribe.

To create an item in a custom vocabulary, you need to define two values. They are the phrase and what you want it to display as

My custom vocabulary defines player to Player and repositoriesies to repositories

![Custom Vocabulary](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1542c25d-ea3b-5dc5-87fc-a77416aabb87_e3f4g5h6)

## Vocabulary Filters

Another feature in Transcribe is vocabulary filtering, which is a feature that blocks out words you don’t want to appear in your transcripts. It's different from custom vocabularies because  custom vocabularies don't block out words .

My vocabulary filter removes words specified in my filler filter txt file. To set up this filter, I first created a txt file with the words i want filtered out

### ✍️ What are we doing in this step?

In this step, I will create a new transcription job with your filter and custom vocabulary and review the improved transcription output and subtitles.

![Vocabulary Filters](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1542c25d-ea3b-5dc5-87fc-a77416aabb87_u7v8w9x0)

## Enhanced Transcription

### I ran a new transcription with my custom vocabulary and filtering settings

The enhanced transcription is better than the baseline because filler words have been removed and the phrases specified have been improved

![Enhanced Transcription](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1542c25d-ea3b-5dc5-87fc-a77416aabb87_k1l2m3n4)

## Real Time Transcription

For my project extension, I experimented with real-time transcription, which converts speech to text instantly i.e. as the speaker is still talking.
