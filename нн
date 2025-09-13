meme_dict = {
            "КРИНЖ": "Что-то очень странное или стыдное",
            "ЛОЛ": "Что-то очень смешное"
            }
while True:
    word = input("Введите непонятное слово (большими буквами!): ")
    if word in meme_dict.keys():
        print(word, meme_dict[word])
    else:
        print('Такого слова нет')
        print('Хотите добавить в словарь')
        if input().lower() == 'да':
            value = input('Введите значение')
            meme_dict[word] = value
