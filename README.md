# Object Oriented Programming
## Objects and classes
The methodology of OOP is rooted in our view of nature. One way to explain this is trying to describe the world. If we try to paint it as a picture, it will miss an important part of it. If we try to depict it as a list of roles everyone has in it (humans, animals, plants), it won't be enough. Instead, when we think about the concept of a human or a dog, we image a few properties they each have and what type of behavior they have. As soon as we detail the attributes and behaviors of all these objects in our world, the picture doesn't only have color but it becomes animated, too. 


This idea of data+behavior as a single unit is the driving force behind OOP. Each one of us has a name, organs and actions we can take. The name, for example, is what makes us different but, the organs is what unifies us. If we put all the common attributes and actions for all human beings, we have ourselves a "template" for any human. We call this a class. The class Human is the starting point of each human. Gabriel, though, isn't a class. He is, what we call, an instance of the class Human, he's an object. Gabriel can eat, walk and talk. But, eating, walking and talking isn't data, it is his "behavior" or, in the world of programming, his methods. This doesn't mean that two objects with the same attributes and methods are the same object. But, that's not important right now. Another, classic, example is the class Dog. The class defines a few attributes, such as 4 legs, 2 eyes and a nose. Each appearance of a dog in the world is an instance of Dog. Some have a name, some don't, some have white hair, some brown. Each breathing, walking and barking dog out there is an instance of the class Dog. But, enough talk, let's look at some code.

```python
class Dog:
    legs = 4
    eyes = 2
    nose = 1

    def __init__(self, name=None):
        self.name = name

my_dog = Dog('Snoop')
street_dog = Dog()
```

In the above example I "bred" two dogs from the class Dog. The class Dog has a few attributes, legs eyes and nose while each Dog instance/object has their own attribute, name. Whenever an object is instantiated, the `__init__` method is called with any arguments we send it. This method is meant to give the object its attributes and they are usually defined there. 

```python
>>> my_dog = Dog('Dooby')
>>> his_dog = Dog('Rex')
>>> her_dog = Dog('Scooby')
>>> print(his_dog.name)
Rex
>>> print(her_dog.name)
Scooby
>>> print(her_dog + my_dog)
ScoobyDooby
```

Object attributes and methods are accessed using a dot between the object and the attribute. Let's give our Dog class some methods (behavior).

```python
class Dog:
    legs = 4
    eyes = 2
    nose = 1

    def __init__(self, name=None):
        self.name = name

    def happy(self):
        ascii = """
                             ;\ 
                            |' \ 
         _                  ; : ; 
        / `-.              /: : | 
       |  ,-.`-.          ,': : | 
       \  :  `. `.       ,'-. : | 
        \ ;    ;  `-.__,'    `-.| 
         \ ;   ;  :::  ,::'`:.  `. 
          \ `-. :  `    :.    `.  \ 
           \   \    ,   ;   ,:    (\ 
            \   :., :.    ,'o)): ` `-. 
           ,/,' ;' ,::"'`.`---'   `.  `-._ 
         ,/  :  ; '"      `;'          ,--`. 
        ;/   :; ;             ,:'     (   ,:) 
          ,.,:.    ; ,:.,  ,-._ `.     \""'/ 
          '::'     `:'`  ,'(  \`._____.-'"' 
             ;,   ;  `.  `. `._`-.  \\ 
             ;:.  ;:       `-._`-.\  \`. 
              '`:. :        |' `. `\  ) \ 
      -hrr-      ` ;:       |    `--\__,' 
                   '`      ,' 
                        ,-' 
        """
        print(ascii)

    def sit(self):
        ascii = r"""
              _=,_
           o_/6 /#\
           \__ |##/
            ='|--\
              /   #'-.
              \#|_   _'-. /
               |/ \_( # |" 
       snd    C/ ,--___/
        """
        print(ascii)

    def lie_down(self):
        ascii = """
                __
               /\/'-,
       ,--'''''   /"
 ____,'.  )       \___
'\"\"\"\"\"------'\"\"\"`-----'
pb
        """
        print(ascii)

    def growl(self):
        ascii = r"""
            |\
   \`-. _.._| \
    |_,'  __`. \
    (.\ _/.| _  |
   ,'      __ \ |
 ,'     __/||\  |
(Y8P  ,/|||||/  |
   `-'_----    /
      /`-._.-'/
      `-.__.-' jg

        """
        print(ascii)

    def eat(self, food):
        if food == 'dog treat':
            self.happy()
        else:
            self.growl()


>>> dog = Dog('Snoopy')
>>> dog.sit()

              _=,_
           o_/6 /#\
           \__ |##/
            ='|--\
              /   #'-.
              \#|_   _'-. /
               |/ \_( # |" 
       snd    C/ ,--___/
        

>>> dog.lie_down()

                __
               /\/'-,
       ,--'''''   /"
 ____,'.  )       \___
'"""""------'"""`-----'
pb
        

>>> dog.eat('healthy food')

            |\
   \`-. _.._| \
    |_,'  __`. \
    (.\ _/.| _  |
   ,'      __ \ |
 ,'     __/||\  |
(Y8P  ,/|||||/  |
   `-'_----    /
      /`-._.-'/
      `-.__.-' jg

        

>>> dog.eat('dog treat')

                             ;\ 
                            |' \ 
         _                  ; : ; 
        / `-.              /: : | 
       |  ,-.`-.          ,': : | 
       \  :  `. `.       ,'-. : | 
        \ ;    ;  `-.__,'    `-.| 
         \ ;   ;  :::  ,::'`:.  `. 
          \ `-. :  `    :.    `.  \ 
           \   \    ,   ;   ,:    (\ 
            \   :., :.    ,'o)): ` `-. 
           ,/,' ;' ,::"'`.`---'   `.  `-._ 
         ,/  :  ; '"      `;'          ,--`. 
        ;/   :; ;             ,:'     (   ,:) 
          ,.,:.    ; ,:.,  ,-._ `.     ""'/ 
          '::'     `:'`  ,'(  \`._____.-'"' 
             ;,   ;  `.  `. `._`-.  \ 
             ;:.  ;:       `-._`-.\  \`. 
              '`:. :        |' `. `\  ) \ 
      -hrr-      ` ;:       |    `--\__,' 
                   '`      ,' 
                        ,-' 
        

```

Over here we gave it a few fun examples that let the dog sit, lie_down, growl, eat and happy. In other words, we gave our Dog some abilities through these new methods. In the above method calls, we see that its first argument `self` isn't explicitly sent. It is implicitly sent as `dog`, our object. Any other argument, such as `food` in our example, are sent like any other function we've used/wrote so far. Methods remind us of functions, and rightfully so. A method is a function bound to an object. The best way to describe an object is as an encapsulation of some data and some functionality. So, we'll have variables and functions thrown in the mix. 

```python
class Human:
    def __init__(self, name, eye_color):
        self.name = name
        self.eye_color = eye_color

    def say(self, something):
        print(something)

    def introduce(self):
        message = f"My name is {self.name} and I have {self.eye_color} eyes."
        self.say(message)

>>> person1 = Human('Jeff', 'blue')
>>> person2 = Human('Helen', 'brown')
>>> person3 = Human("Dra'nakyuek, Destroyer of Worlds", 'black')
>>> person1.say("Hello")
Hello
>>> person2.introduce()
My name is Helen and I have brown eyes.
```

Another example, albeit shorter, in which we used the object attribute from its method. We defined a class, Human, with no class attributes but we created 3 instances of Human. Our person1-3 are 3 objects of type Human. Each with an attribute of name and eye_color. Each with a couple of methods that allow them to "do" something. This time, though, we used some of the attributes of each instance inside the method. Namely, their name and eye_color when they wanted to introduce themselves. The variable `self` is only available inside the methods. This is easily discerned as it's in the method signature. Kind of like a function and the argument it receives. Kind of.


The point here is to differentiate between a class and an object. They are not interchangable. There is also a difference between class attributes that all objects share and object attributes that "belong" to that object only. Objects can access class attributes and all instances of that class will "see" the same values. But, object attributes aren't accessible in the same way between different instances. Those must be passed as arguments, like any other variable.

## Inheritance
Class inheritance is the ability to pass down attributes and methods to another class. Think about genetics in human beings. We've inherited the traits of our fathers and mothers. If both your parents have blue eyes, you'll have blue eyes\*. In programming, this tool allows us to write more efficiently. Let's look at some examples
```python
class Human:
    eyes = 2
    nose = 1


class Asian(Human):
    skin_color = 'yellow'
    smart = True


class Cyclopse(Human):
    eyes = 1
    evil = True


class French(Human):
    nationality = 'French'
```

What we've done here is create a single base class and a few classes that inherit from it. Whatever attributes the class Human had, it will pass down to those who inherit from it. For example, it doesn't matter where you are born or who your ancestors are, such as our Asian class, you still are Human. If a class inherits an attribute but overwrites its value, it will, then, have that new value. 

```python
class Dog:
    eyes = 2
    nose = 1

class Terrier(Dog):
    breed = 'Terrier'

class Bulldog(Dog):
    breed = 'Bulldog'


>>> dog1 = Terrier()
>>> print(dog1.breed)
Terrier
>>> dog2 = Bulldog()
>>> print(dog2.breed)
Bulldog
```

Classic example of dog breeds inheriting from Dog. All dogs have 2 eyes and a nose but they can introduce their own different attributes which will be available to any instance of that class.
>Create a Car base class with 2 models inheriting from it. Give the Car class a couple of relevant attributes and have the inherited models add a unique attribute, each.

```python
class Dog:
    def __init__(self, dog_name):
        self.name = dog_name


class Terrier(Dog):
    breed = 'Terrier'
    nose = 'long'


class Bulldog(Dog):
    breed = 'Bulldog'
    nose = 'flat'

>>> pet1 = Bulldog('T-Rex')
>>> pet2 = Terrier('Vadar')
>>> print(pet1.name)
T-Rex
>>> print(pet2.name)
Vadar
```

Unless we specify a new `__init__` method, the parent class' method will be called whenever a new inherited class instance is created. 

```python
class Dog:
    def __init__(self, dog_name):
        self.name = dog_name


class Terrier(Dog):
    breed = 'Terrier'

    def __init__(self, dog_name, hair_color):
        super().__init__(dog_name)
        self.hair_color = hair_color

>>> pet = Terrier('Luke', 'black')
>>> print(pet.hair_color)
black
```

If we wanted to add some functionality to the inherited class instantiating process, we can override the `__init__` method but without forgetting to use the parent `__init__` method. It is a strongly recommended standard to call the parent method before anything else and we do so with `super().__init__(...)`.

>Augment your car model classes with `__init__` methods. The base class should define a `gear` attribute (manual/automatic) and the inheriting classes with `headlight_type` attribute.

## Multiple inheritance
Usually a headache and rarely mandatory but, nonetheless, it is a core attribute of OOP. This gives us the ability to have one class inherit from multiple classes at the same time. For example, a Bull Terrier inherits from both a Bulldog and a Terrier. He has a long nose but short legs. Each trait he inherited from a different parent. In programming, we can do something similar by creating a new class that inherits attributes and methods from other classes.

```python
class Dog:
    def __init__(self, dog_name):
        self.name = dog_name


class Terrier(Dog):
    breed = 'Terrier'
    nose = 'long'


class Bulldog(Dog):
    breed = 'Bulldog'
    nose = 'flat'


class BullTerrier(Terrier, Bulldog):
    breed = 'Bull Terrier'


>>> alien = BullTerrier('Danger')
>>> print(alien.nose)
long
```

Whatever unique properties each class has will be inherited 'as-is' by any inheriting classes. Problem is, what happens when the same attribute exists in two classes? On the surface, it looks as if Python will look through the inherited classes left to right and select the first class that has the attribute. But, that isn't entirely true. It is only true for simple cases. Let's look at another example.

```python
class X():
    def who_am_i(self):
        print("I am a X")
    
class Y():
    def who_am_i(self):
        print("I am a Y")
    
class A(X, Y):
    def who_am_i(self):
        print("I am a A")
    
class B(Y, X):
     def who_am_i(self):
         print("I am a B")

class F (A, B):
    def who_am_i(self):
        print("I am a F")

# RIP MRO
```

This raises an error. The algorith responsible for deciding "where to go" is called MRO - Method Resolution Order. While it builds the order in which it resolves how to select methods, its algorithm must determine that there is a good a baseclass for each class. What is a good baseclass? That no two or more children multiple-inherit from it in different order. If you want to know more, please look at a detailed explanation found [here](https://makina-corpus.com/blog/metier/2014/python-tutorial-understanding-python-mro-class-search-path).

>Create a car model with a sunroof and another with a bike rack. Have a new car model inherit from both and use these two attributes.


In the industry, multiple inheritance are rarely used. Please, think carefully if you decide to do so. It increases code complexity and maintenance.

## OOP and Python
A core aspect of OOP is private attributes (properties and methods) that aren't available to anyone using an instance of that class. Even though the property/method are defined, they cannot be accessed/called outside the class code. If you instantiate an object of that class, you cannot use these private attributes. The reasoning behind this is to protect the programmer from making mistakes when using the object. For example, imagine a class responsible for providing the current time to anyone who asks and it does so according to a \_ntp_ip attribute pointing to a NTP server IP. But this attribute, \_ntp_ip, isn't changed, internally, without validating that the host is up using a private method \_validate_ip(ip). A programmer using this class can make the mistake of changing the NTP server address directly, without checking it is up, first. This is risky and can, potentially, break the program. Other examples can be a complex algorithm broken down to multiple methods that aren't meant to be used seperately.


Python allows access to private attributes and methods. I know we've built a case against it but Python assumes we're all mature programmers and know what we're doing. That, if we choose to use a private attribute or method, we have a very good reason to do it. The notation for private attributes is an underscore prefix `_ntp_ip`. Generally speaking, there isn't a reason to use private attributes outside the class code as they were made not to be used - And, most likely, for a good reason. 

>Write a program made up of a class `TellTime` that tells the time according to an NTP server when the method `now()` is called. Write a `set_ntp_ip(ip)` method that uses private attributes, of your engineering, to verify the IP and set it, if all is well.

Python has a number of special methods that allow us to augment the behavior of an object. For example, we can create a class that, when instantiated, will react to the plus operator, e.g. `TellTime() + 10`. In programming, this is called operator overloading. This code is executed however we define under the method `__add__` of our class `TellTime`. There are other such special methods that fall under the Python Data Model but don't overload operators and aren't called operator overloading. Such as `__getitem__` that is called when we write `TellTime()['key']`. We instantiated an object of type TellTime and accessed it like a dictionary using brackets. Whatever logic we put inside `__getitem__` is entirely of our choose. A useful method is `__str__` that let's us easily use the object in a print statement. Imagine our clock has many attributes and we want to print what time it is, instead of formatting the code using several of its properties, we can define `__str__` once and refer to our object as a str. It will automagically transform to a string. `__str__` is expected to return a string. Let's look at some examples that use +=, str and [].

```python
class CountDown:
    def __init__(self):
        self.hour = 6
        self.minute = 30
        self.second = 0

    def __iadd__(self, value):
        """Adds seconds to the count down!"""
        self.second += value
        self.minute += self.second//60
        self.hour += self.minute//60
        self.second = int((self.second/60 - self.second//60)*60)
        self.minute = int((self.minute/60 - self.minute//60)*60)
        self.hour = int((self.hour/60 - self.hour//60)*60)

        return self

    def __str__(self):
        """Prettify the count down status."""
        parts = []
        if self.hour > 0:
            parts.append(f"{self.hour} hours")
        if self.minute > 0:
            parts.append(f"{self.minute} minutes")
        if self.second > 0:
            parts.append(f"{self.second} seconds")

        if not parts:
            return "You're time is up!"

        last = parts.pop()
        commas = ','.join(parts)

        return f"You have {commas} and {last} left."

    def __getitem__(self, item_name):
        """Access the properties like a dict."""
        if item_name == 'hour':
            return self.hour
        elif item_name == 'minute':
            return self.minute
        elif item_name == 'second':
            return self.second
        else:
            return ''


>>> final_cd = CountDown()
>>> print(f"We know there's {final_cd.hour} hours, {final_cd.minute} minutes and {final_cd.second} seconds left.")
We know there's 6 hours, 30 minutes and 0 seconds left.
>>> final_cd += 60
>>> print(f"{final_cd}")
You have 6 hours and 31 minutes left.
```

When we use the `for` loop on an object, the method `__iter__` is called. The method `__iter__` is expected to return an iterable object, such as a list, which `for` will use to cycle through items. Let's use this Python ability to write some grey magic. When you write code that uses complex Python internals that can hardly be explained, it becomes black magic. But, we aren't evil, we'll stick with a little intuitive code.

```python
class Student:
    """Defines one student."""
    def __init__(self, id_num, name, mark):
        self.id_num = id_num
        self.name = name
        self.mark = mark


class PythonClass:
    """Defines a Python class of students using a given list of Student objects.."""
    def __init__(self, students):
        """
        :param students: list of Student
        """
        self.students = students

    def __iter__(self):
        marks = [s.mark for s in self.students]
        return marks


>>> ptclass = PythonClass([Student("100200300", "Gabe", 80),
                     Student("200300100", "Ella", 95),
                     Student("300100200", "Merkel", -200)])
>>> print("The marks are: ")
>>> for mark in ptclass:
>>>     print(mark)
The marks are: 
80
95
-200
```

>Create a AttackPlan class that has a list of Victim objects as an instance property. Each Victim has a property of IP and MAC address. When AttackPlan is used as an iterator, under `for` for example, return the list of Victim IPs.

## Finals
Let's create a bank. Write a code that allows us to manage a bank. It'll include 3 account types, Account, BusinessAccount and PrivateAccount. We'll also have the accounts container class, Bank. We'll work our way from the bottom to the top. Firstly, create a base class `Account` that has the properties account_id, name, account_type and balance. It should also have the methods that allow it to add to its balance and deduct from its balance. Implement an easy way to print the account name and balance. Secondly, create a `PrivateAccount` and `BusinessAccount` class that inherit from `Account` but, `PrivateAccount` has a limit of how much it can withdraw from its account, at 30000 while `BusinessAccount` does not. Finally, implement a `Bank` class that has a name, address and list of accounts. It should have a method `create` that allows to create a new account. This method should ask the user details about the account, including its type, before it is added to the list of accounts in that bank.


If you're feeling brave - Implement support for withdrawing and depositing different currencies. One approach to this is having `balance` property as a new object type and not `int`. Then, each time a withdraw or deposit operation is done, we'll use this new type to determine conversion rate and, ultimately, how much money should go in/out.


If you're feeling very brave - Implement support for different currencies using real time conversion rates you pull off the internet.