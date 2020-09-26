# FaceDetectionOpenCV

Датасет не большой! Качество готовой модели будет низкое!

## Извлечение контрольных точек для тренировки модели:
python extract_embeddings.py --dataset dataset --embeddings output/embeddings.pickle --detector face_detection_model --embedding-model openface.nn4.small2.v1.t7

## Тренировка модели по извлеченным точкам:
python train_model.py --embeddings output/embeddings.pickle --recognizer output/recognizer.pickle --le output/le.pickle

## Проверка модели по изображениям не учавствоваших в тренировки:
python recognize.py --detector face_detection_model --embedding-model openface.nn4.small2.v1.t7 --recognizer output/recognizer.pickle --le output/le.pickle --image images\JaredLeto.jpg

## Определение лиц с вебкамеры:
python recognize_video.py --detector face_detection_model --embedding-model openface.nn4.small2.v1.t7 --recognizer output/recognizer.pickle --le output/le.pickle
