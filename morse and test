from unittest import TestCase

codes_ru = {
    "А": ".-",
    "Б": "-...",
    "В": ".--",
    "Г": "--.",
    "Д": "-..",
    "Е": ".",
    "Ж": "...-",
    "З": "--..",
    "И": "..",
    "Й": ".---",
    "К": "-.-",
    "Л": ".-..",
    "М": "--",
    "Н": "-.",
    "О": "---",
    "П": ".--.",
    "Р": ".-.",
    "С": "...",
    "Т": "-",
    "У": "..-",
    "Ф": "..-.",
    "Х": "....",
    "Ц": "-.-.",
    "Ч": "---.",
    "Ш": "----",
    "Щ": "--.-",
    "Ъ": "--.--",
    "Ы": "-.--",
    "Ь": "-..-",
    "Э": "..-..",
    "Ю": "..--",
    "Я": ".-.-",
    "1": ".----",
    "2": "..---",
    "3": "...--",
    "4": "....-",
    "5": ".....",
    "6": "-....",
    "7": "--...",
    "8": "---..",
    "9": "----.",
    "0": "-----",
    ".": "......",
    ",": ".-.-.-",
    ":": "---...",
    ";": "-.-.-.",
    "(": "-.--.-",
    ")": "-.--.-",
    "'": ".----.",
    '"': ".-..-.",
    "-": "-....-",
    "/": "-..-.",
    "?": "..--..",
    "!": "--..--",
    "@": ".--.-.",
    "=": "-...-",
    " ": " ",
}

codes_en = {
    "A": ".-",
    "B": "-...",
    "C": "-.-.",
    "D": "-..",
    "E": ".",
    "F": "..-.",
    "G": "--.",
    "H": "....",
    "I": "..",
    "J": ".---",
    "K": "-.-",
    "L": ".-..",
    "M": "--",
    "N": "-.",
    "O": "---",
    "P": ".--.",
    "Q": "--.-",
    "R": ".-.",
    "S": "...",
    "T": "-",
    "U": "..-",
    "V": "...-",
    "W": ".--",
    "X": "-..-",
    "Y": "-.--",
    "Z": "--..",
    "1": ".----",
    "2": "..---",
    "3": "...--",
    "4": "....-",
    "5": ".....",
    "6": "-....",
    "7": "--...",
    "8": "---..",
    "9": "----.",
    "0": "-----",
    ", ": "--..--",
    ".": ".-.-.-",
    "?": "..--..",
    "/": "-..-.",
    "-": "-....-",
    "(": "-.--.",
    ")": "-.--.-",
}


def text2morse(msg, lang="ru"):
    # Проверка доступных языков
    if lang not in ("en", "ru"):
        raise ValueError("Language is not supported")
    if lang == "ru":
        codes = codes_ru
    elif lang == "en":
        codes = codes_en
    # Проверка типа входящего сообщения
    if not isinstance(msg, str):
        raise TypeError("Wrong msg type")
    # Проверка разрешенных символов
    for char in set(msg.upper()):
        if char not in codes.keys():
            raise ValueError(f"Out of allowed character set: {str(list(codes.keys()))}")

    return " ".join([codes[i] for i in msg.upper()])


class TestMorse(TestCase):
    def test_str(self):
        self.assertEqual(text2morse("Привет", lang="ru"), ".--. .-. .. .-- . -")
        self.assertEqual(text2morse("Hello", lang="en"), ".... . .-.. .-.. ---")

    def test_wrong_lang(self):
        with self.assertRaises(ValueError):
            text2morse("Hello", lang="ru")
            text2morse("Привет", lang="en")
            text2morse("Hello", lang="XX")

    def test_instance(self):
        self.assertIsInstance(text2morse("Привет", lang="ru"), str)
        self.assertIsInstance(text2morse("Hello", lang="en"), str)


# if __name__ == "__main__":
#     text = input("Введите текст кирилицей: ")
#     converted = text2morse(text)
#     print(f"Ваш текст азбукой Морзе будет: {converted}")
