import time, random, threading
from seleniumwire import webdriver  # Import from seleniumwire
# how much bots
count = 35
#don´t change i
i = 0

def start():
    # Put the proxy.txt in the same folder like the script
    lines = open("proxy.txt").read().splitlines()
    Proxy = random.choice(lines)
    print("Proxy IP: " + Proxy)
    
    options = {
        'proxy': {
            'socks5': 'socks5://'+ Proxy,
            'no_proxy': 'localhost,127.0.0.1' # excludes
        }
    }
       
    # other chrome options
    chrome_options = webdriver.ChromeOptions()
    chrome_options.add_argument('--headless')
    chrome_options.add_argument('--no-sandbox')
    chrome_options.add_argument('--ignore-certificate-errors-spki-list')
    chrome_options.add_argument('--ignore-ssl-errors')

    # Create a new instance of the Chrome driver
    driver = webdriver.Chrome(options=chrome_options,seleniumwire_options=options)
    
    # Go to the Google home page
    print('\nStart Settings\n')
    driver.get('chrome://settings/')
    time.sleep(5)
    print('\n Im on Twitch \n')
    
    # Here Twitch Link to Streamer
    driver.get('https://www.twitch.tv/geiles_brot1')
    
    # Access requests via the `requests` attribute
    for request in driver.requests:
        if request.response:
            print(
                request.url,
                request.response.status_code,
                request.response.headers['Content-Type']
            )
    time.sleep(5000)

while count > i:
    threading.Thread(target=start).start()  
    i += 1
    print('\nNummer ' + str(i) + '\n')
    time.sleep(20)
