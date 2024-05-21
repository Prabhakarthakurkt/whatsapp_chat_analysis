# whatsapp_chat_analysis

    import pandas as pd 
    import numpy as np 
    import seaborn as sn
    import matplotlib.pyplot as plt 
    import re
    import datatime as dt 
    %matplotlib inline 


'''
Importing the text file which contains the chat of the group in  read mode using utf -8 encoding ! 
This is my clg group chat, it contains chats from 2023, so its a very big file , will preview it after we've done regular expressions ! 



'''

      f = oper('whatsApp Chat with 2018-2022 IT-B (1).txt', 'r' ,encoding='utf-8')
      data = f.read()


      dummy =data.split('\n')
      dummy 

'''
Example for dry run :
'''


# username  and message in differnet col 

    pattern = ''
    message = re.split(pattern,data)[1:]
    print(len(messages))

## extracting dates as well in different col 

   dates = re.findell(pattern, data)
   print(len(dates))

##  This is a simple time string, we will apply this kind of transformation 
## inorder to get the date and the time for our anylysis 


     string = ''
     string = string.split(',')
     date,time= string[0],string[1]
     time = time.split('_')
     time = time[0].strip()
     print(date+" and "+time)


# this function is to sperate the time and date 

     def gettimeanddate(string):
        string  =  string.split(',')
        date,time = string[0],string[1]
        time = time.split('__')
        time = time[0].sptip()
        print(date+ " and " +time)

# this function is to seperate the time and date 

        def gettimeanddate(string)
            string = string.split(',')
            date,time = string[0],string[1]
            time = time.split('_')
            time = time[0].strip()

            return date+" "+time

# creating a dateframe for messages and their dates 

         def = pd.DateFrame({'user_messeges' : messages, 'message_date': dates})
         df.rename(columns={'messages_date':'date'},inplace=Ture)

         df.head()


         df['user_messeges']

'''
if we observe the usermessege,we find that the userneme is attached with the user messeges, so i need to get rid of this , for that i will use the concept of this regular expression .

  sample of the regular expression output 

   ['' , 'Chinmayee', 'Hello this is official grup\n']

  so here we can see that the username is at index 1 and message is at index2

  sometimes it happens that we get the group notification , so for that case we have to handle it accordingly!


 Chinmayee: Hello this is offical grup 

  Chinmayee added you \n-->['Chinmayee added you','\n']

         
         
         
         
  '''

         users = []
         messege =[]

         for messege in df['user_messeges']:
              entry = re.split('([w\w]+?):\s',message)
              if entry[1:]:
                users.append(entry[1])
                messeges.append(endtry[2])
              else:
                users.append('Group Notification')
                messeges.append(entry[0])

      df['user] = users
      df['messages'] = messages

      def getstring(text):
         return text.split('\n')[0]
      df['message'] = df['message'].apply(lambda text:getstring(text))

      df = df.drop(['user_messages'],axis=1)
      df = df[['message','date', 'user']]

      df = df.rename(columns={'message':'Message','date':'Date'})
      df.head()


      df.shape

      df['Only date'] = pd.to_datetime(df['Date']).dt.date

      df['Year'] = pd.to_datetime(df['Date']).dt.year

      df['Month_num'] = pd.to_datetime(df['Date'].dt.month

      df['Month'] = pd.to_datetime(df['Date']).dt.day

      df['Day']=pd.

              
