# PM2.5 Patterns in Four Major Chinese Cities (January-August 2021)
**Final Project, Computing and Research Methods for Climate Data Science**  
Wenzhuo Tian (wt2394)

## Research question and hypotheses

I want to compare how PM2.5 changes from late winter into summer across four major Chinese cities, and check whether cities differ in their seasonal-transition strength and in their daily commuting-hour pattern. The four cities (Shanghai, Chengdu, Guangzhou, and Shenyang) span coastal, inland-basin, southern, and northern settings.

**Hypothesis 1.** Northern/inland cities (Shenyang, Chengdu) should show a larger late-winter-to-summer PM2.5 drop than coastal/southern cities (Shanghai, Guangzhou), because of stronger heating-season emissions and more stable winter boundary layers in the north.

**Hypothesis 2.** Within each city, PM2.5 during morning and evening commute hours should be higher than midday PM2.5, due to traffic plus a shallow nocturnal/early-morning boundary layer.

## Datasets

The notebook pulls hourly station observations from the OpenAQ v3 API. An Open-Meteo fallback is included in case OpenAQ data isn't available, but in this run all four cities come from OpenAQ.

- OpenAQ v3 API: https://docs.openaq.org/
- Open-Meteo Air Quality API (fallback): https://open-meteo.com/en/docs/air-quality-api

All API calls happen inside the notebook, so there are no manual download steps.

## Three-sentence analysis summary

The notebook loads hourly OpenAQ PM2.5 for Shanghai, Chengdu, Guangzhou, and Shenyang from January through early August 2021, and cleans the data into one Pandas DataFrame. It then groups by month, by period (Late Winter, Spring, Summer), and by hour of day to compare seasonal and diurnal patterns across the four cities. Finally, it tests both hypotheses using late-winter-minus-summer differences and commute-vs-midday t-tests, with results shown in six labeled figures.

