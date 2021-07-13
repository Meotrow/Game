# Game
class animal(object):





    def __init__(self,Name, Hunger = 0, Boredom=0):

        self.name=Name

        self.hunger=Hunger

        self.boredom=Boredom

        print("Привет, я зверюшка по имени "+self.name)

    def Talk(self):

        print("Привет, меня зовут "+self.name+"\n", " Сейчас мое настроение ", self.mood())

    def __pass_time(self):

        self.hunger+=2

        self.boredom+=2

    def mood(self):

        mood=self.hunger+self.boredom

        if mood<10:

            f="безупречно"

        elif 10<=mood<=20:

            f="нормальное"

        elif 20<=mood<=30:

            f="не очень"

        else:

            f="плохое, меня хотят отправить на выставку"

        return f

    def eat(self,ammount):

        if self.hunger<ammount:

            print("Я уже покушал, спасибо за заботу!")

        elif self.hunger>=3:

            self.hunger-=ammount

            print("Спасибо за этот(эти) прекрасный(е) бигмак(и)!!!")

            self.__pass_time()

    def play_in_Dota3(self):

        if self.boredom<3:

            print("Я устал от этих руинеров, не хочу больше играть")

        elif self.boredom>=3:

            self.boredom-=3

            print("Спасибо, за то что сыграл со мной эту катку !! Теперь мне намного лучше")

        self.__pass_time()

    def __str__(self):

        return "Настроение: "+str(self.boredom)+"\t Сытость: "+str(self.hunger)











animal1=animal("Тима")

animal1.hunger=4

animal1.boredom=4

choise=None

while choise != "0":

    print \

        ("""

        0 - Выход 

        1 - Узнать настроение зверюшки 

        2 - Покормить зверюшку

        3 - Поиграть со зверюшкой в Доту 3





       """)

    choise=input()

    if choise=="1":

        animal1.Talk()

    elif choise=="2":



        animal1.eat(int(input("Введите количество бигмаков ")))



    elif choise=="3":

        animal1.play_in_Dota3()

    elif choise=="state":

        print(animal1)



    else:

        print("Простите, я вас не понимаю! Выберите пункт из меню. Для того, чтобы узнать голод и настроение введите state")



