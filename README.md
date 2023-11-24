<img src="https://capsule-render.vercel.app/api?type=waving&height=300&text=Prompirit"/>

# Prompirit: Prompt Editing AI Tool to Create AI-Generative Work Using User Emotion

“이미지 GenAI 프롬프트 최적화를 제공하는 Prompirit은 사용자 발화 및 사용자 감정의 키워드를 분석하는 Multi-modal AI 프롬프트 엔지니어링 도구를 사용해 
text prompt를 생성한 후, 이를 GenAI의 input 프롬프트로 활용하여 사용자의 감정을 보다 정교하게 반영한 이미지 결과물을 생성하도록 한다.”
<br/>
<br/>

## 목차
- [제안내용](#제안내용)
- [Research Questions](#research-questions)
- [구현방법](#구현방법)
- [세부기술](#세부기술)
- [Contribution](#contribution)
- [References](#references)

<br/>

 ## 제안내용
 Expressing emotions is a crucial behavior that benefits humans in various ways, such as enriching self-expression, self-awareness, and creativity. Recently, a number of generative AI models have been steadily mentioned to support this process by creating images through short text prompts. However, it is still uncertain whether generated images show user emotions in text prompts properly. In this paper, we propose a multi-modal prompt engineering AI tool, Prompirit, that improves AI-generated images by using user’s emotions as a core feature. First we will curate a rubric to apply emotions in text prompts more precisely with automatic prompt engineering. With our rubric, we will make an attempt to improve the output image by adding voice and face data for emotion recognition. After that, we will conduct user study to confirm the effectiveness of Prompirit.
<br/>
<br/>
감정 표현은 자기표현, 자기인식, 창의성을 풍부하게 하는 등 여러 방면에서 인간에게 도움이 되는 중요한 행동입니다. 최근 생성형 AI는 이러한 과정을 지원하는 도구로써 꾸준히 언급되고 있습니다. 그러나 생성된 이미지가 텍스트 프롬프트 내 사용자의 감정을 명확히 반영하는지는 여전히 불확실합니다. 본 논문에서는 사용자의 감정을 핵심 요소로 고려하여 AI 생성 이미지를 개선하는 멀티모달 프롬프트 엔지니어링 AI 도구인 Prompirit을 제안합니다. 먼저 자동화된 프롬프트 엔지니어링을 통해 텍스트 프롬프트에서 감정을 보다 정확하게 반영하도록 하는 루브릭을 만들 것입니다. 또한, 출력 이미지를 개선하기 위해, 음성 및 얼굴 데이터를 추가하여 감정 인식 정확도를 높이는 시도를 할 것입니다. 이후 Prompirit의 효과를 확인하기 위한 사용자 연구를 수행할 것입니다.
<br/>
<br/>

## Research Questions
**RQ1.** How can emotions in text prompts be applied to generated image more precisely with automatic engineering? <br/>
**RQ2.** How can emotion and information requests of image generative AI users be observed more precisely? <br/>
**RQ3.** How effective is Prompirit in generating images with emotional expression? <br/>
<br/>

## 구현방법
**RQ1. 어떻게 하면 자동화된 텍스트 프롬프트 엔지니어링을 통해 텍스트 내의 감정을 더욱 정교하게 이미지 결과물에 반영할 수 있는가?**
- 선행연구인 RePrompt에서 사용된 process인 단어 단위 텍스트 분석을 문장 단위 텍스트 분석과 비교
- 분석한 텍스트를 최적화된 프롬프트 형태로 가공
- CLIP score 계산을 통해 효과적이었던 방식을 rubric으로 채택
<br/>

**RQ2. 어떻게 하면 이미지 생성 AI 사용자의 감정 및 정보 요청을 더욱 명확히 파악할 수 있는가?**
- multi-modal (bi-modal, tri-modal) 방식을 도입함
- uni-modal vs multi-modal (bi-modal, tri-modal) 에서 인식된 감정 및 텍스트를 프롬프트 형식으로 가공 후 이미지 생성
- CLIP score를 계산하여 객관적인 측정 지표로 사용해 비교
<br/>

**RQ3. Prompirit이 감정을 반영하는 이미지를 생성함에 있어서 얼마나 더 효과적인가?**
- 유저 스터디: 사용자의 얼굴, 음성, 텍스트를 수집하여 RQ1&RQ2의 방식으로 조합해 각각 이미지 생성 → 어떤 이미지가 감정을 가장 잘 반영하였는가 선택

<br/>

## 세부기술
PyTorch<br/>
OpenCV<br/>
Generative AI - Stable diffusion / DALL.E<br/>
Multi-modal Emotion Recognition - Tensor Fusion Network<br/>
Training Dataset (multi modal) - 영어(CMU-MOSI)/한국어(AI-Hub 멀티모달 영상)<br/>
Multi-class sentiment analysis - KoBERT <br/>
<br/>

## Contribution
1. 텍스트의 감정 맥락을 정교하게 읽을 수 있는 멀티모달 AI를 통해 주어진 프롬프트 감정 맥락에 적합한 이미지를 생성할 수 있음
2. human-readable prompt revisions: 사용자가 모델을 더 잘 이해하고 trial-and-error 시도 횟수를 줄이도록 함
3. 정신의학(심리 상담, 스트레스 조절, expressive writing 등)에 활용될 수 있음
<br/>

## References
[1] Yunlong Wang, Shuyuan Shen, and Brian Y. Lim. 2023. RePrompt: Automatic Prompt Editing to Refine AI-Generative Art Towards Precise Expressions. In Proceedings of the 2023 CHI Conference on Human Factors in Computing Systems (CHI ’23), April 23–28, 2023, Hamburg, Germany. ACM, New York, NY, USA, 29 pages. https://doi.org/10.1145/3544548.3581402
<br/>
[2] Jonas Oppenlaender. 2022. Prompt Engineering for Text-Based Generative Art. arXiv 1, 1. Retrieved from http://arxiv.org/abs/2204.13988
<br/>
[3] Ankita Gandhi, Kinjal Adhvaryu, Soujanya Poria, Erik Cambria, Amir Hussain, Multimodal sentiment analysis: A systematic review of history, datasets, multimodal fusion methods, applications, challenges and future directions, Information Fusion, Volume 91, 2023, Pages 424-444, ISSN 1566-2535, https://doi.org/10.1016/j.inffus.2022.09.025.
<br/>
[4] Amir Zadeh, Minghai Chen, Soujanya Poria, Erik Cambria, and Louis-Philippe Morency. 2017. Tensor Fusion Network for Multimodal Sentiment Analysis. In Proceedings of the 2017 Conference on Empirical Methods in Natural Language Processing, pages 1103–1114, Copenhagen, Denmark. Association for Computational Linguistics.
<br/>
[5] Andrea Scarantino. 2017. How to Do Things with Emotional Expressions: The Theory of Affective Pragmatics. Psychological Inquiry 28, 2–3: 165–185. https://doi.org/10.1080/1047840X.2017.1328951
