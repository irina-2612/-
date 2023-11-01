# Классификация пациентов с ишемической болезнью сердца

## Оглавление
1. Описание проекта
2. Какой кейс решаем
3. Краткая информация о данных
4. Этапы работы над проектом
5. Результат
6. Выводы

### 1. Описание проекта
Ишемическая болезнь сердца - состояние, вызываемое хроническим недостаточным снабжением клеток сердечной мышцы кислородом (гипоксия) и питательными веществами. Наиболее частой причиной этого является накопление атеросклеротических бляшек в коронарных артериях. Характерными симптомами ИБС считают одышку и появление стенокардии (боль в груди). В начале ухудшение кровотока может не вызывать симптомов, поэтому иногда даже серьёзное осложнение — инфаркт миокарда (сердечный приступ) — возникает без видимых заранее признаков и симптомов. ИБС является основной причиной смерти в мире по данным ВОЗ за 2019 год.

Факторы риска подразделяют на немодифицируемые (которые невозможно контролировать) и модифицируемые, включают курение, недостаточную физическую активность, избыточный вес и несбалансированное питание. Для профилактики ИБС рекомендуется изменение образа жизни (отказ от алкоголя и курения, правильное питание и физические упражнения), а для лечения, кроме изменения образа жизни, назначают лекарства: статины, антикоагулянты и антиагреганты, бета-блокаторы и другие препараты. В некоторых случаях показаны хирургические вмешательства.

ИБС диагностируют на основании симптомов и анамнеза: врач должен спросить о пищевых привычках, физической активности, перенесённых заболеваниях, семейной истории, оценить факторы риска сердечно-сосудистых заболеваний, провести обследования, с помощью которых можно диагностировать ИБС и попытаться предсказать потенциальный риск возникновения инфаркта миокарда.

Первым и самым важным действием для лечения ИБС и профилактики её осложнений наравне с медикаментозными и хирургическими методами является изменение образа жизни: отказ от курения, увеличение физической активности, правильное питание.

Цель проекта на основании данных о пациенте предсказать наличие у него Ишемической болезни сердца с целью раннего выявления и начала профилактики и лечения для минимизации последствий

### 2. Какой кейс решаем
Необходимо создать модель, которая позволит предсказать наличие у пациента ишемической болезни сердца

**Метрика качества**\
В качестве метрики качества в модели применяется recall и f1. Цель добится значения метрики recall выше 0,95.


### 3. Краткая информация о данных
База данных с данными о пациентах: CAD.csv

**Демографические:**  
Age - возраст  30-86 лет  
Weight - Вес 48-120  
Length - Рост  
Sex - пол мужской, женский  
BMI - ИМТ (индекс массы тела, Кг/м2) 18-41  
DM - СД (сахарный диабет) Да, нет  
HTN - гипертоническая болезнь (гипертонус) Да, нет  
Current Smoker - курильщик в настоящее время Да, нет  
EX-Smoker - бывший курильщик Да, нет  
FH - семейный анамнез да, нет  
Obesity - Ожирение Да, если MBI > 25, в противном случае нет  
CRF - ХПН (хроническая почечная недостаточность) Да, нет  
CVA (нарушение мозгового кровообращения) Да, нет  
Airway disease - заболевание дыхательных путей Да, нет  
Thyroid Disease - заболевание щитовидной железы Да, нет  
CHF - ХСН (застойная сердечная недостаточность) Да, нет  
DLP - ДЛП (дислипидемия) Да, нет  

**Симптомы и обследование :**
BP - АД (кровяное давление: мм рт. ст.) 90-190  
PR (частота пульса) (промилле) 50-110  
Edema - отек Да, нет  
Weak Peripheral Pulse - слабый периферический пульс Да, нет  
Lung rales - легочные хрипы Да, нет  
Systolic Murmur - систолический шум Да, нет  
Diastolic Murmur - диастолический шум Да, нет  
Typical Chest Pain - типичная боль в груди Да, нет  
Dyspnea - одышка Да, нет  
Function Class - функциональный класс 1, 2, 3, 4  
Atypical - нетипичный Да, нет  
Nonanginal - неангинальный ХП Да, нет  
Exertional CP - ХП при физической нагрузке (боль в груди при физической нагрузке) Да, нет  
LowTH Ang - низкопороговая стенокардия (low Threshold angina) Да, нет  

**ЭКГ:**  
нарушение ритма, ФП  
Q Wave - зубец Q Да, нет  
St Elevation - повышение уровня ST Да, нет  
St Depression - депрессия сегмента ST Да, нет  
LVH - инверсия Т Да, нет  
LVH - ГЛЖ (гипертрофия левого желудочка) Да, нет  
Poor R Progression - слабое прогрессирование зубца R (слабое прогрессирование зубца R) Да, нет  

**Лабораторные исследования и эхо:**  
FBS - (уровень сахара в крови натощак) (мг/дл) 62-400  
Cr  - (креатин) (мг/дл) 0,5–2,2  
TG - уровень ТГ (триглицеридов) (мг/дл) 37-1050  
LDL - уровень ЛПНП (липопротеинов низкой плотности) (мг/дл) 18-232  
HDL - уровень ЛПВП (липопротеинов высокой плотности) (мг/дл) 15-111  
BUN - (азот мочевины крови) (мг/дл) 6-52  
ESR - СОЭ (скорость оседания эритроцитов) (мм/ч) 1-90  
HB  - (hemoglobin) (g/dl) 8.9–17.6  
K - (potassium) (mEq/lit) 3.0–6.6  
Na - (sodium) (mEq/lit) 128–156  
WBC - лейкоциты (WBC) (клетки/мл) 3700-18000  
Lymph - лимфа (лимфоциты) (%) 7-60  
Neut - (нейтрофилы) (%) 32-89  
PLT - (тромбоциты) (1000/мл) 25-742  
EF - (фракция выброса) (%) 15-60  
Region RWMA - Область с RWMA (аномалия движения региональной стенки) 0, 1, 2, 3, 4  
VHD (клапанная болезнь сердца) Нормальная, легкая, умеренная, тяжелая  
Cath - целевой показатель


### 4. Этапы работы над проектом
1. Анализ и обработка данных
2. Построение моделей


### 5. Результат
Максимальное значение метрик удалось достичь при применении модели на основе случайного леса, с подобранными параметрами. Цель по метрике достигнута.

### 6. Выводы