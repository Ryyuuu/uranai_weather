# デザイン
class pycolor:
    ACCENT = '\033[01m' #強調
    END = '\033[0m'

# 天気を調べる
import requests
import json

def get_current_weather(city_name):
    API_KEY = "cff32b3d73a4904677884f57ee9c597f"
    api = "http://api.openweathermap.org/data/2.5/weather?units=metric&q={city}&APPID={key}"

    url = api.format(city=city_name, key=API_KEY)

    # 気象情報を取得
    response = requests.get(url).json()
    # APIレスポンスの表示
    jsonText = json.dumps(response, indent=2)
    # print(jsonText)
    Response=response["weather"][0]
    ave=response["main"]["temp"]
    m=response["main"]["temp_min"]
    M=response["main"]["temp_max"]
    return Response["description"],ave,m,M #天気,平均気温,最低気温,最高気温

def research():
  City=["Sapporo","Sendai","Tokyo","Niigata","Nagoya","Osaka","Hiroshima","Kochi","Fukuoka","Naha"]
  Cnum=["1","2","3","4","5","6","7","8","9","10"]
  CITY=dict(zip(Cnum,City))
  A=input("占いついでに現在の天気・気候を調べられます。調べますか？　調べる場合は「はい」を入力してください")
  if A=="はい":
    city_name=input("どの都市を調べますか？以下から番号を1つ選んでください\n1.札幌 2.仙台 3.東京 4.新潟 5.名古屋 6.大阪 7.広島 8.高知 9.福岡 10.那覇　")
    City_name=CITY[city_name]
    AA=get_current_weather(City_name)
    return f"☁☀現在の天気は{AA[0]},平均気温は{AA[1]},最低気温は{AA[2]},最高気温は{AA[3]}です☀☁"
  else:
    return "またのご利用、お待ちしています"
    
def judge(s):
  try:
      int(s)
      return  True
  except ValueError:
      return False
      
# 名前
import re
def 名前():
  while True:
    inf1=input("質問1：あなたの名前の総画数を教えてください！ ")

    pattern0_0=r"(.+)画"
    pattern0_1=r".+"
    if "画" in inf1:
      pattern=re.compile(pattern0_0)
    else:
      pattern=re.compile(pattern0_1)
    name=pattern.findall(inf1)

    number=["一","二","三","四","五","六","七","八","九"]
    Number=["1","2","3","4","5","6","7","8","9"]
    way=0
    for i in range(9):
      if number[i] in name[0]:
        way=1
        break
    if way==1:
      num=list(name[0])
      d=dict(zip(number,Number))
      if len(num)==1:
        if num[0]=="十":
          name=10
        else:
          name=d(num[0])
      elif len(num)==2:
        if num[0]=="十":
          name="1"+(d[num[1]])
        else:
          name=d[num[0]]+"0"
      else:
        name=d[num[0]]+d[num[2]]
    if way==0:
      name=name[0]

    if judge(name)==True:
      return name
      break
    else:
      print("正しい入力ではありません。\nもう一度入力してください。")
      
# 生年月日      
def 誕生日():
  pattern1_0=r"\d\d\d\d\d?\d\d?\d"
  pattern1_1=r'(\d\d\d\d)年(\d\d?)月(\d\d?)日'
  pattern1_2=r"(\d\d\d\d).(\d\d?).(\d\d?)"
  pattern1_3=r"(昭和|平成|令和)(\d\d?)年(\d\d?)月(\d\d?)日"
  pattern1_4=r"(\d\d\d\d)年の(昨日|今日|明日)"
  pattern1_5=r"(\d\d\d\d)-(\d\d?)-(\d\d?)"
  pattern1_6=r"(\d\d\d\d)/(\d\d?)/(\d\d?)"

  while True:
    inf2=input("質問2：あなたの生年月日を教えてください！")
    In=0
    IN=0
    if "年" in inf2:
      if "昭和" in inf2 or "平成" in inf2 or "令和" in inf2:
        In=1
        IN=1
        pattern=re.compile(pattern1_3)
        break
      elif "昨日" in inf2 or "今日" in inf2 or "明日" in inf2:
        In=1
        IN=3
        pattern=re.compile(pattern1_4)
        break
      else:
        In=1
        IN=2
        pattern=re.compile(pattern1_1)
        break
    elif "." in inf2:
      In=1
      IN=2
      pattern=re.compile(pattern1_2)
      break
    elif "-" in inf2:
      In=1
      IN=2
      pattern=re.compile(pattern1_5)
      break
    elif "/" in inf2:
      In=1
      IN=2
      pattern=re.compile(pattern1_6)
      break
    elif judge(inf2)==True:
      if len(inf2)==8 or  len(inf2)==7 or  len(inf2)==6:
        In=1
        IN=4
        pattern=re.compile(pattern1_0)
        break
      else:
        print("正しい入力ではありません。\nもう一度入力してください。")
    else:
      print("正しい入力ではありません。\nもう一度入力してください。")

  if In==1:
    result=pattern.findall(inf2)

  if IN==1:
    if result[0][0]=="令和":
      A=str(int(result[0][1])+18)
      b="20"+A
    elif result[0][0]=="平成":
      if len(result[0][1])==2:
        A=int("20"+result[0][1])
      else:
        A=int("200"+result[0][1])
      b=str(A-12)
    elif result[0][0]=="昭和":
      A=str(int(result[0][1])+25)
      b="19"+A
    birth=b+result[0][2]+result[0][3]

  if IN==2:
    year=list(result[0][0])
    month=list(result[0][1])
    day=list(result[0][2])
    if len(month)==1:
      month.insert(0,0)
    if len(day)==1:
      day.insert(0,0)
    birth=year+month+day
    birth="".join(map(str,birth))

  if IN==3:
    today=datetime.now()
    if result[0][1]=="今日":
      a=today.strftime("%m%d")
    elif result[0][1]=="昨日":
      yesterday=today-timedelta(days=1)
      a=yesterday.strftime("%m%d")
    elif result[0][1]=="明日":
      tomorrow=today+timedelta(days=1)
      a=tomorrow.strftime("%m%d")
    birth=result[0][0]+str(a)

  if IN==4:
    result=result[0]
    check=result[:4]
    if len(result)==6:
      birth=check+str(0)+result[4:5]+str(0)+result[5:]
    elif len(result)==7:
      a=result[4:5]
      b=result[5:]
      A=result[4:6]
      B=result[6:]
      if int(A)>12:
        birth=check+str(0)+a+b
      else:
        while True:
          month=input(f"あなたの誕生月は{a}月ですか？それとも{A}月ですか？\n{a}または{A}のどちらか一方を入力してください")
          if month==a:
            birth=check+str(0)+a+b
            break
          elif month==A:
            birth=check+A+str(0)+B
            break
          else:
            print("正しい入力ではありません。\nもう一度入力してください。")
    else:
      birth=result

  return birth    
  
def 約数(n):
  num=[]
  for i in range(1, int((n+1)**0.5)+1):
      if n % i == 0:
          num.append(i)
          num.append(n//i)
  num=list(set(num))
  return num
from datetime import datetime,timedelta

def feeling_weather():
  name_ans=名前()
  birth_ans=誕生日()

  Today=datetime.now()
  today=Today.strftime("%Y%m%d")
  weekend=Today.weekday()

  sum=0
  for i in range(7):
    SUM=birth_ans[i]+today[7-i]
    sum+=int(SUM)
  Num=約数(weekend)+約数(int(name_ans))
  Num=list(set(Num))

  if 1<=sum<=30:
    ans=sum
  else:
    while sum>28:
      for i in Num:
        sum-=i
    ans=sum
  
  if ans%7==0:
    return pycolor.ACCENT+"☀今日のあなたの気分予報結果☀：快晴　　今日1日気持ち良く過ごせるでしょう！"+pycolor.END
  elif ans%weekend==0:
    return pycolor.ACCENT+"☀今日のあなたの気分予報結果☀：晴れ　　今日1日平穏に過ごせるでしょう！"+pycolor.END
  return pycolor.ACCENT+"☔今日のあなたの気分予報結果☀：曇りのち晴れ☀　　午後に気分が上がる出来事が起きるでしょう！"+pycolor.END  
