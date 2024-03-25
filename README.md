# TrafficLLM :red_car: :blue_car: 

## Description 🚦
This is a machine learning project aimed to create a traffic LLM that can provide comprehensive traffic forecasts and live summaries for users.

## Dataset 🚷
1. Singapore Traffic Images with Vehicle Count (2023): This is a new dataset containing ~700k road camera traffic images with vehicle counts collated specifically for this project. Traffic camera image data is pulled from data.gov.sg API and the annotation of vehicle count is done automatically using YOLOv5 objection detection. Dataset is now public for use on [Kaggle](https://www.kaggle.com/datasets/jaydenteoh/singapore-traffic-images-with-vehicle-count-2023/code?datasetId=4651666)
2. Llama-2-7b-chat-hf + Mistral-7B-Instruct-v0.1: This dataset is created by prompt engineering the LLMs on randomly-generated Singaporean traffic live data to produce summaries for finetuning a smaller language model

## Notebooks 🖥️
- `traffic-route-visualisation.ipynb`: explaratory visualization of the traffic around Singapore and route planning using Google Maps API
- `traffic_data_collection.ipynb`: data collection and annotation of vehicle counts across Singapore in 2023 using traffic camera images
- `traffic_forecast_model_training.ipynb`: using data collected to train MLP models for each traffic camera to forecast the traffic along each Singaporean road
- `chatbot_distillation.ipynb`: leveraging knowledge distillation to distil the abstrative summarization capabilties of LLMs (specifically Llama-2-7b-chat-hf and Mistral-7B-Instruct-v0.1) to finetune a 8-bit quantized smaller language model (Microsoft Phi-2) with LoRA adapters

## Models 📈
1. `camera_{CAMERA_ID}_model.h5`: these are MLP models created by `traffic_forecast_model_training.ipynb` for forecasting traffic on a road for which the traffic camera is installed. The forecasting abilities of these specialized models are quite decent.
2. TrafficLLM PeftModel: To be released soon. Will be releasing the finetuned lora adapters for producing traffic forecasting and recommendations using small language models.
