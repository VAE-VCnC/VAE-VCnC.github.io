<h2><center> Unifying One-Shot Voice Conversion and Cloning with Disentangled Speech Representations </center></h2>

<h2>0. Contents</h2>
1. [Abstract](#abstract)
2. [Comparison models and their implementations](#implementations)
3. [Voice Conversion Samples](#vc-comp)
4. [Voice Cloning Samples](#vcl-comp)

<h2>1. Abstract<a name="abstract"></a></h2>

We propose unifying one-shot voice conversion and cloning into a single model that can be end-to-end optimized. To achieve this, we introduce a novel extension to a speech variational auto-encoder (VAE) that disentangles speech into content and speaker representations. Instead of using a fixed Gaussian prior as in the vanilla VAE, we incorporate a learnable text-aware prior as an informative guide for learning the content representation. This results in a content representation with reduced speaker information and more accurate linguistic information. The proposed model can sample the content representation using either the posterior conditioned on speech or the text-aware prior with textual input, enabling one-shot voice conversion and cloning, respectively. Experiments show that the proposed method achieves better or comparable overall performance for one-shot voice conversion and cloning compared to state-of-the-art voice conversion and cloning methods.


<h2>2. Comparison models and their implementations<a name="implementations"></a></h2>

<h3>Below lists the compared models we used in our experiments. We adopt the same test set for all of them.</h3>

[SC-GlowTTS: Google Colab](https://colab.research.google.com/drive/1yyQDc-xWCqa2g-d1joW_goqbYZKaImsJ?usp=sharing)

[CDFSE: https://github.com/thuhcsi/interspeech2022-cdfse-tts](https://github.com/thuhcsi/interspeech2022-cdfse-tts)

[VQMIVC: https://github.com/Wendison/VQMIVC](https://github.com/Wendison/VQMIVC)

[VAE-GP: http://arxiv.org/abs/2210.13771](http://arxiv.org/abs/2210.13771)

<h3>The below official Hifi-GAN pre-trained model is used.</h3>

[Hifi-GAN (official): VCTK-V1](https://drive.google.com/drive/folders/1vJlfkwR7Uyheq2U5HrPnfTm-tzwuNuey)

<h2>3. Voice Conversion Samples<a name="vc-comp"></a></h2>

| ID | **Source** | **Reference** | **VQMIVC**  |**SC-GlowTTS**| **VAE-GP** | **VAE-TP(ours)**|
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 |<audio src="wavs/voice_conversion/0.hifi-gan-src/vc-p225_017-to-p238.wav" controls preload></audio> | <audio src="wavs/targets/vc-p225_017-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_conversion/1.vqmivc/vc-p225_017-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_conversion/2.sc-glowtts/vc-p225_017-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_conversion/3.vvc/vc-p225_017-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_conversion/4.vvcc/vc-p225_017-to-p238.wav" controls preload></audio> |
| 2 |<audio src="wavs/voice_conversion/0.hifi-gan-src/vc-p225_258-to-p302.wav" controls preload></audio> | <audio src="wavs/targets/vc-p225_258-to-p302.wav" controls preload></audio> | <audio src="wavs/voice_conversion/1.vqmivc/vc-p225_258-to-p302.wav" controls preload></audio> | <audio src="wavs/voice_conversion/2.sc-glowtts/vc-p225_258-to-p302.wav" controls preload></audio> | <audio src="wavs/voice_conversion/3.vvc/vc-p225_258-to-p302.wav" controls preload></audio> | <audio src="wavs/voice_conversion/4.vvcc/vc-p225_258-to-p302.wav" controls preload></audio> |
| 3 |<audio src="wavs/voice_conversion/0.hifi-gan-src/vc-p234_109-to-p245.wav" controls preload></audio> | <audio src="wavs/targets/vc-p234_109-to-p245.wav" controls preload></audio> | <audio src="wavs/voice_conversion/1.vqmivc/vc-p234_109-to-p245.wav" controls preload></audio> | <audio src="wavs/voice_conversion/2.sc-glowtts/vc-p234_109-to-p245.wav" controls preload></audio> | <audio src="wavs/voice_conversion/3.vvc/vc-p234_109-to-p245.wav" controls preload></audio> | <audio src="wavs/voice_conversion/4.vvcc/vc-p234_109-to-p245.wav" controls preload></audio> |
| 4 |<audio src="wavs/voice_conversion/0.hifi-gan-src/vc-p234_115-to-p294.wav" controls preload></audio> | <audio src="wavs/targets/vc-p234_115-to-p294.wav" controls preload></audio> | <audio src="wavs/voice_conversion/1.vqmivc/vc-p234_115-to-p294.wav" controls preload></audio> | <audio src="wavs/voice_conversion/2.sc-glowtts/vc-p234_115-to-p294.wav" controls preload></audio> | <audio src="wavs/voice_conversion/3.vvc/vc-p234_115-to-p294.wav" controls preload></audio> | <audio src="wavs/voice_conversion/4.vvcc/vc-p234_115-to-p294.wav" controls preload></audio> |
| 5 |<audio src="wavs/voice_conversion/0.hifi-gan-src/vc-p238_021-to-p347.wav" controls preload></audio> | <audio src="wavs/targets/vc-p238_021-to-p347.wav" controls preload></audio> | <audio src="wavs/voice_conversion/1.vqmivc/vc-p238_021-to-p347.wav" controls preload></audio> | <audio src="wavs/voice_conversion/2.sc-glowtts/vc-p238_021-to-p347.wav" controls preload></audio> | <audio src="wavs/voice_conversion/3.vvc/vc-p238_021-to-p347.wav" controls preload></audio> | <audio src="wavs/voice_conversion/4.vvcc/vc-p238_021-to-p347.wav" controls preload></audio> |
| 6 |<audio src="wavs/voice_conversion/0.hifi-gan-src/vc-p238_114-to-p225.wav" controls preload></audio> | <audio src="wavs/targets/vc-p238_114-to-p225.wav" controls preload></audio> | <audio src="wavs/voice_conversion/1.vqmivc/vc-p238_114-to-p225.wav" controls preload></audio> | <audio src="wavs/voice_conversion/2.sc-glowtts/vc-p238_114-to-p225.wav" controls preload></audio> | <audio src="wavs/voice_conversion/3.vvc/vc-p238_114-to-p225.wav" controls preload></audio> | <audio src="wavs/voice_conversion/4.vvcc/vc-p238_114-to-p225.wav" controls preload></audio> |
| 7 |<audio src="wavs/voice_conversion/0.hifi-gan-src/vc-p302_029-to-p234.wav" controls preload></audio> | <audio src="wavs/targets/vc-p302_029-to-p234.wav" controls preload></audio> | <audio src="wavs/voice_conversion/1.vqmivc/vc-p302_029-to-p234.wav" controls preload></audio> | <audio src="wavs/voice_conversion/2.sc-glowtts/vc-p302_029-to-p234.wav" controls preload></audio> | <audio src="wavs/voice_conversion/3.vvc/vc-p302_029-to-p234.wav" controls preload></audio> | <audio src="wavs/voice_conversion/4.vvcc/vc-p302_029-to-p234.wav" controls preload></audio> |
| 8 |<audio src="wavs/voice_conversion/0.hifi-gan-src/vc-p302_034-to-p326.wav" controls preload></audio> | <audio src="wavs/targets/vc-p302_034-to-p326.wav" controls preload></audio> | <audio src="wavs/voice_conversion/1.vqmivc/vc-p302_034-to-p326.wav" controls preload></audio> | <audio src="wavs/voice_conversion/2.sc-glowtts/vc-p302_034-to-p326.wav" controls preload></audio> | <audio src="wavs/voice_conversion/3.vvc/vc-p302_034-to-p326.wav" controls preload></audio> | <audio src="wavs/voice_conversion/4.vvcc/vc-p302_034-to-p326.wav" controls preload></audio> |
| 9 |<audio src="wavs/voice_conversion/0.hifi-gan-src/vc-p326_350-to-p261.wav" controls preload></audio> | <audio src="wavs/targets/vc-p326_350-to-p261.wav" controls preload></audio> | <audio src="wavs/voice_conversion/1.vqmivc/vc-p326_350-to-p261.wav" controls preload></audio> | <audio src="wavs/voice_conversion/2.sc-glowtts/vc-p326_350-to-p261.wav" controls preload></audio> | <audio src="wavs/voice_conversion/3.vvc/vc-p326_350-to-p261.wav" controls preload></audio> | <audio src="wavs/voice_conversion/4.vvcc/vc-p326_350-to-p261.wav" controls preload></audio> |
| 10 |<audio src="wavs/voice_conversion/0.hifi-gan-src/vc-p326_350-to-p347.wav" controls preload></audio> | <audio src="wavs/targets/vc-p326_350-to-p347.wav" controls preload></audio> | <audio src="wavs/voice_conversion/1.vqmivc/vc-p326_350-to-p347.wav" controls preload></audio> | <audio src="wavs/voice_conversion/2.sc-glowtts/vc-p326_350-to-p347.wav" controls preload></audio> | <audio src="wavs/voice_conversion/3.vvc/vc-p326_350-to-p347.wav" controls preload></audio> | <audio src="wavs/voice_conversion/4.vvcc/vc-p326_350-to-p347.wav" controls preload></audio> |
| 11 |<audio src="wavs/voice_conversion/0.hifi-gan-src/vc-p347_336-to-p238.wav" controls preload></audio> | <audio src="wavs/targets/vc-p347_336-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_conversion/1.vqmivc/vc-p347_336-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_conversion/2.sc-glowtts/vc-p347_336-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_conversion/3.vvc/vc-p347_336-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_conversion/4.vvcc/vc-p347_336-to-p238.wav" controls preload></audio> |
| 12 |<audio src="wavs/voice_conversion/0.hifi-gan-src/vc-p347_405-to-p238.wav" controls preload></audio> | <audio src="wavs/targets/vc-p347_405-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_conversion/1.vqmivc/vc-p347_405-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_conversion/2.sc-glowtts/vc-p347_405-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_conversion/3.vvc/vc-p347_405-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_conversion/4.vvcc/vc-p347_405-to-p238.wav" controls preload></audio> |
| --- | --- | --- | --- | --- | --- | --- |

<h2>3. Voice Cloning Samples<a name="vcl-comp"></a></h2>

(1) Its creed provides for the protection of all men in their rights of worship according to the dictates of conscience.

| **Reference** |**SC-GlowTTS**| **CDFSE** | **VAE-TP(ours)**|
| :--- | :--- | :--- | :--- |
| <audio src="wavs/voice_cloning/6.hifi-gan-tgt/tts-10-to-p225.wav" controls preload></audio> | <audio src="wavs/voice_cloning/2.sc-glowtts/tts-9-to-p225.wav" controls preload></audio> | <audio src="wavs/voice_cloning/5.cdfse/tts-9-to-p225.wav" controls preload></audio> | <audio src="wavs/voice_cloning/4.vvcc/tts-9-to-p225.wav" controls preload></audio> |
| --- | --- | --- | --- |

(2) He thought he detected a pleasant smell of herbs, like the potpourri his mother had in bowls in their house.

| **Reference** |**SC-GlowTTS**| **CDFSE** | **VAE-TP(ours)**|
| :--- | :--- | :--- | :--- |
| <audio src="wavs/voice_cloning/6.hifi-gan-tgt/tts-6-to-p234.wav" controls preload></audio> | <audio src="wavs/voice_cloning/2.sc-glowtts/tts-1-to-p234.wav" controls preload></audio> | <audio src="wavs/voice_cloning/5.cdfse/tts-1-to-p234.wav" controls preload></audio> | <audio src="wavs/voice_cloning/4.vvcc/tts-1-to-p234.wav" controls preload></audio> |
| --- | --- | --- | --- |

(3) Poor Rachel! her nature recoiled from deceit, and she told, at all events, as much of the truth as she dared.

| **Reference** |**SC-GlowTTS**| **CDFSE** | **VAE-TP(ours)**|
| :--- | :--- | :--- | :--- |
| <audio src="wavs/voice_cloning/6.hifi-gan-tgt/tts-31-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_cloning/2.sc-glowtts/tts-30-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_cloning/5.cdfse/tts-30-to-p238.wav" controls preload></audio> | <audio src="wavs/voice_cloning/4.vvcc/tts-30-to-p238.wav" controls preload></audio> |
| --- | --- | --- | --- |

(4) She lay awake very long this night, planning how to lessen the evil influence of their Milton life on her mother.

| **Reference** |**SC-GlowTTS**| **CDFSE** | **VAE-TP(ours)**|
| :--- | :--- | :--- | :--- |
| <audio src="wavs/voice_cloning/6.hifi-gan-tgt/tts-36-to-p245.wav" controls preload></audio> | <audio src="wavs/voice_cloning/2.sc-glowtts/tts-28-to-p245.wav" controls preload></audio> | <audio src="wavs/voice_cloning/5.cdfse/tts-28-to-p245.wav" controls preload></audio> | <audio src="wavs/voice_cloning/4.vvcc/tts-28-to-p245.wav" controls preload></audio> |
| --- | --- | --- | --- |

(5) When we came up I told Miller to shut the bank door, which they had left open in their hurry.

| **Reference** |**SC-GlowTTS**| **CDFSE** | **VAE-TP(ours)**|
| :--- | :--- | :--- | :--- |
| <audio src="wavs/voice_cloning/6.hifi-gan-tgt/tts-37-to-p248.wav" controls preload></audio> | <audio src="wavs/voice_cloning/2.sc-glowtts/tts-2-to-p248.wav" controls preload></audio> | <audio src="wavs/voice_cloning/5.cdfse/tts-2-to-p248.wav" controls preload></audio> | <audio src="wavs/voice_cloning/4.vvcc/tts-2-to-p248.wav" controls preload></audio> |
| --- | --- | --- | --- |

(6) Rodolfo meanwhile having returned home, and having missed the crucifix, guessed who had taken it, but gave himself no concern about it.

| **Reference** |**SC-GlowTTS**| **CDFSE** | **VAE-TP(ours)**|
| :--- | :--- | :--- | :--- |
| <audio src="wavs/voice_cloning/6.hifi-gan-tgt/tts-13-to-p261.wav" controls preload></audio> | <audio src="wavs/voice_cloning/2.sc-glowtts/tts-6-to-p261.wav" controls preload></audio> | <audio src="wavs/voice_cloning/5.cdfse/tts-6-to-p261.wav" controls preload></audio> | <audio src="wavs/voice_cloning/4.vvcc/tts-6-to-p261.wav" controls preload></audio> |
| --- | --- | --- | --- |

(7) Only, even though love has wholly disappeared, she still claims consideration, and Althea did not wish to lose Hermon's regard.

| **Reference** |**SC-GlowTTS**| **CDFSE** | **VAE-TP(ours)**|
| :--- | :--- | :--- | :--- |
| <audio src="wavs/voice_cloning/6.hifi-gan-tgt/tts-44-to-p294.wav" controls preload></audio> | <audio src="wavs/voice_cloning/2.sc-glowtts/tts-47-to-p294.wav" controls preload></audio> | <audio src="wavs/voice_cloning/5.cdfse/tts-47-to-p294.wav" controls preload></audio> | <audio src="wavs/voice_cloning/4.vvcc/tts-47-to-p294.wav" controls preload></audio> |
| --- | --- | --- | --- |

(8) Very much of squalor and discomfort will be endured before the last trinket or the last pretense of pecuniary decency is put away.

| **Reference** |**SC-GlowTTS**| **CDFSE** | **VAE-TP(ours)**|
| :--- | :--- | :--- | :--- |
| <audio src="wavs/voice_cloning/6.hifi-gan-tgt/tts-8-to-p302.wav" controls preload></audio> | <audio src="wavs/voice_cloning/2.sc-glowtts/tts-4-to-p302.wav" controls preload></audio> | <audio src="wavs/voice_cloning/5.cdfse/tts-4-to-p302.wav" controls preload></audio> | <audio src="wavs/voice_cloning/4.vvcc/tts-4-to-p302.wav" controls preload></audio> |
| --- | --- | --- | --- |

(9) So the Castrato began to speak him fair and say to him, O my lord, take this purse and go with me.

| **Reference** |**SC-GlowTTS**| **CDFSE** | **VAE-TP(ours)**|
| :--- | :--- | :--- | :--- |
| <audio src="wavs/voice_cloning/6.hifi-gan-tgt/tts-21-to-p326.wav" controls preload></audio> | <audio src="wavs/voice_cloning/2.sc-glowtts/tts-14-to-p326.wav" controls preload></audio> | <audio src="wavs/voice_cloning/5.cdfse/tts-14-to-p326.wav" controls preload></audio> | <audio src="wavs/voice_cloning/4.vvcc/tts-14-to-p326.wav" controls preload></audio> |
| --- | --- | --- | --- |

(10) The marquis of Worcester, a man past eighty four, was the last in England that submitted to the authority of the parliament.

| **Reference** |**SC-GlowTTS**| **CDFSE** | **VAE-TP(ours)**|
| :--- | :--- | :--- | :--- |
| <audio src="wavs/voice_cloning/6.hifi-gan-tgt/tts-45-to-p335.wav" controls preload></audio> | <audio src="wavs/voice_cloning/2.sc-glowtts/tts-20-to-p335.wav" controls preload></audio> | <audio src="wavs/voice_cloning/5.cdfse/tts-20-to-p335.wav" controls preload></audio> | <audio src="wavs/voice_cloning/4.vvcc/tts-20-to-p335.wav" controls preload></audio> |
| --- | --- | --- | --- |

(11) I will briefly describe them to you, and you shall read the account of them at your leisure in the sacred registers.

| **Reference** |**SC-GlowTTS**| **CDFSE** | **VAE-TP(ours)**|
| :--- | :--- | :--- | :--- |
| <audio src="wavs/voice_cloning/6.hifi-gan-tgt/tts-4-to-p347.wav" controls preload></audio> | <audio src="wavs/voice_cloning/2.sc-glowtts/tts-22-to-p347.wav" controls preload></audio> | <audio src="wavs/voice_cloning/5.cdfse/tts-22-to-p347.wav" controls preload></audio> | <audio src="wavs/voice_cloning/4.vvcc/tts-22-to-p347.wav" controls preload></audio> |
| --- | --- | --- | --- |
