# Импортируйте необходимые библиотеки:
import requests
from bs4 import BeautifulSoup
# Напишите функцию для проверки доступности сайта:
def check_site_availability(url):
    """
    Проверяет наличие сайта по указанному URL.

    :param url: URL сайта для проверки.
    :return: True, если сайт доступен, False - если нет.
    """

    # Делаем запрос к указанному URL
    try:
        response = requests.get(url, timeout=5)
        if response.status_code == requests.codes.ok:
            return True
        else:
            return False
    except requests.RequestException:
        return False
# Функция использует библиотеку requests для отправки GET-запроса на указанный URL и проверяет статус ответа. Если статус ответа равен 200 (код состояния OK), то сайт доступен. Если запрос не удается или статус ответа не равен 200, то сайт считается недоступным.
