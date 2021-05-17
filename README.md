# covid19_Update_bot
![Screenshot (153)](https://user-images.githubusercontent.com/38040515/118494167-7d6c3c00-b73f-11eb-8406-502545a6729b.png)

![Screenshot (155)](https://user-images.githubusercontent.com/38040515/118494564-ea7fd180-b73f-11eb-90e9-eb25d1e7fc0a.png)
updates the corona cases in India via slack channel

Features:

-> update on new Corona Virus cases happening in India

-> Slack notification on updates

-> How many Indian nationals have Corona Virus per State?

-> How many deaths happened per State?

-> How many people are vaccinated?

-> The updates can be limited to specific states

-> Its reliable as the data is from Government official site "https://www.mygov.in/"


Required: 

* Python

* Slack account + Slack Webhook url to send slack notifications to your account

slack_webhook_url = 'https://hooks.slack.com/services/<slack webhook url>'
  
* dependencies required

requests #send html requests
BeautifulSoup #align html data and for data scraping
json
tabulate #converting data to tabular form
datetime, time
schedule #for scheduling time when to update the cases on slack channel

** You can install the dependencies ---->   pip install <dependency name>

Scheduling time when to update the cases on slack channel:

On linux:

crontab scheduling

crontab -e  #editor

--> To run the bot every day at 10:00 AM (min hr dayofmonth month day)

* * 10 * * * <path to the file> <python compiler path> python3 <filename> 


On windows or jupyter or google colab:

import schedule 

add the code <

schedule.every().day.at("10:00").do(corona_updateCases)
  while True:
    schedule.run_pending()
    time.sleep(1)
    
>  This code runs the file every day at 10:00 AM
