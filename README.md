# logo-detection-prototype

Постановка задачи:
Нужно создать систему, которая по заданным образцам логотипов определяет, присутствует ли логотип искомой организации на изображении, вырезанном из видео с рекламой. Учитывая, что логотипы могут быть разного масштаба, яркости, контраста, повернуты, искажены и немного отличаться в дизайне, система должна быть устойчивой к этим изменениям.


Архитектура системы:

    Извлечение признаков:

        Используется предобученная CNN (ResNet-50) для преобразования обнаруженных логотипов в вектор признаков (эмбеддинги).

    Сравнение с эталонами:

        Заранее вычисляются эмбеддинги для всех образцов логотипов искомой организации.
    
        Для каждого обнаруженного логотипа вычисляется косинусное сходство между его эмбеддингом и эталонными векторами.
    
        Если максимальное сходство превышает пороговое значение, логотип считается принадлежащим целевой организации.

ToDo:
- Детекция логотипа, если кром слишком большой (можно использовать предобученные модели типа YOLO или Faster R-CNN)
- Дообучение ResNet-50 на LogoDet-3K
- Интегрировать OCR (например, Tesseract) для логотипов с текстом
