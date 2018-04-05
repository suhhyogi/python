#Dictionary exercise

def getinfo(): # menu no.1
    for i,j in class_scores.items(): #class score란 딕셔너리 들어있는 name, score 를 프린트한다.
        print("name: {}, score:{}".format(i,j))

def addinfo():# menu no.2
    person_name=input("input name:")
    person_score=int(input("input score: ")) # 입력으로 name, score 를 받는다.
    class_names=class_scores.keys() # 현재 class score 에 저장되 있는 key 를 받는다.
    if person_name in class_names: # 입력받은 name 이 key 값에 있는지 없는지를 확인
        print(" name already exist! insert different name")
        addinfo()
    else: # 없는 값이면, 입력받은 name, score 를 dictionary 에 추가 한다.
        class_scores[person_name]=person_score
        class_scores.update({person_name:person_score})
        getinfo()

def modifyinfo(): #menu No.3
    person_name=input("name for modify:")
    class_names=class_scores.keys()
    if person_name in class_names:
        person_score=int(input("score for modify:"))
        class_scores[person_name]=person_score
        print(" complete!")
        getinfo()
    else:
        print("no name")

def deletinfo(): #menu No.4
    person_name=input("write the name for delete:")
    class_names=class_scores.keys()
    if person_name in class_names:
        class_scores.__delitem__(person_name)
        print("delete complete")
        getinfo()
    else:
        print("No name")

def findinfo(): # menu No.5
    person_name=input("Enter a name to find:")
    class_names=class_scores.keys()
    if person_name in class_names:
        print("The score of {} is {}.".format(person_name, class_name[person_name]))




menu='''
---------------------------
| 1. student information  |
| 2. Add student Info.    |
| 3. Modify Student Info. |
| 4. Delete Student Info. |
| 5. Find Student Info.   |
| 0. system Exit          |
---------------------------
'''

import sys
class_scores={"hong":100, "seo":80, "yeo":90}

while 1:
    print(menu)
    num=int(input("service number:"))

    if num==1:
        getinfo()
    elif num==2:
        addinfo()
    elif num==3:
        modifyinfo()
    elif num==4:
        deletinfo()
    elif num==5:
        findinfo()
    elif num==0:
        sys.exit()
        
