## 1 变量和简单数据类型

* **字符串（单引或双引）修改**
```python
.title() #首字母大写,不改变变量中的值 
.upper() #全部大写,不改变变量中的值 
.lower() #全部小写,不改变变量中的值 用户名的注册等
```
不使用`/n`换行，字符串用三对单引号
``` python
'''hehe
xixi
haha'''
```
* **字符串合并（拼接）**
  使用加号`+`来合并，也可以使用逗号`,`逗号显示为空格
* **删除字符串中空白**
```python
.strip() #删除字符串两端空白
.lstrip() #删除字符串开头空白
.rstrip() #删除字符串末尾空白
```
* **使用`str(age)`函数转换数据类型为字符串**
* **原始字符串(引号开头加r）** `print(r'\'eh')` 输出为`\'eh`




## 2 列表

​				*------适合存储在程序运行期间可能变化的数据集*

* **列表由一系列按特定顺序排列的元素组成**
```python
names = ['a','b','c',1,2.5]
print(names[-1]) #输出最后一个列表元素，-2……同理,列表为空时错误
```
* **确定列表长度**
```python
len(names)
```

* **修改列表元素**
```python
names[index] = 'A'
```
* **添加列表元素**
```python
.append('x') #在列表末尾添加元素
.insert(index,'d')  #在列表任意位置添加元素，既有元素右移一位
```
* **删除列表元素**
```python
del names[0] #知道要删除元素在列表的位置，不再使用它
.pop()或.pop(index) #删除列表末尾元素并能接着使用它；删除任意位置元素并能接着使用它
.remove('a') #只知道要删除元素的值，不知道所处位置
```

* **组织列表**

  * **排序**

  ```python
  .sort() #对列表永久性排序,从小到大
  .sort(reverse=True) #对列表永久性排序,从大到小
  sorted(names) #对列表临时排序,从小到大
  sorted(names,reverse=True) #对列表临时排序,从大到小
  .reverse() #永久反转列表元素的排列顺序
  ```




## 3 操作列表

* **for循环(注意缩进)**

  ```python
  for cat in cats:
  	print('...')
  ```

* **创建数值列表**

  * `range()`**函数返回一系列数字**

    ```python
    #打印1~4
    for value in range(1,5)：
    	print(value)
    ```

  * `list()`**函数可以将**`range()`**的结果转换为列表**

    ```python
    numbers = list(range(1,5)) #1~4
    numbers = list(range(2,11,2)) #2~11（不包括11）每次加2
    ```

  * **对数字列表简单统计运算函数**

    ```python
    min(numbers)
    max(numbers)
    sum(numbers)
    ```

* **`enumerate()`在for循环中拿到索引**

  ```python
  numbers = [1,3,5,7,9]
  for index,number in enumerate(numbers):
      print(index,number)
  ```

* **列表解析（一行代码生成列表）**

  ```python
  numbers = [value**2 for value in range(0,11,2)]
  numbers = [x*x for x in range(1,11,3) if x%2==0] #加条件，x能被2整除
  l = [x+y for x in '123' for y in 'ABC'] #多层for循环
  ```

* **切片------处理列表的部分元素**

  ``` python
  #若没有指定起始索引，从开头开始；没有指定终止索引，到末尾才停止
  numbers = [1,2,3,4,5]
  print(numbers[2:4]) #打印3,4
  print(numbers[-3:]) #打印最后三个3,4,5
  for number in numbers[:3]: #遍历前三个切片
  for number in numbers[::2] #遍历全部，隔一个
  ```

* **复制列表**

  ```python
  my_numbers = [1,3,5,7,9]
  friend_numbers = my_numbers[:] #复制成功，有两个对象指向不同列表
  friend_numbers = my_numbers #两个对象指向同一列表，处理元素时两列表都受影响
  ```

  ​

* **元组------不可变的列表**
  ```python
  demensions = (200,50) # 定义一个尺寸元组
  demensions[0] = 250 #错误的，不能修改
  demensions = (250,500) #可以重新定义赋值
  ```




## 4 if语句

* ```python
  cars = ['toyota','bmw','audi','w']
  for car in cars:
      if car == 'bmw':
          print(car.upper())
      else:
          print(car.title())
  ```

  * 简单if语句
  * if-else语句
  * if-elif-else语句（可省略else,elif结尾）
  * if-if-if（测试多个条件）

* **条件测试**

  * `==`区分大小写，一般提交用户名时用`lower()`方法
  * `!=` 
  	 `and`	
  * `or`
  * `in` 检测特定值是否包含在列表中
  * `not in` 检测特定值是否不包含在列表中`if user not in banned_users:`

* **利用if语句处理列表**

  * **检查特殊元素**

    ```python
    requested_toppings = ['a','b','c']
    for requested_topping in requested_toppings:
        if requested_topping == 'a':
            print('sorry,We are out of a right now.')
        else:
            print('adding:'+requested_topping)
    print('\nFinished making your pizza!')
    ```

  * **确定列表不是空的**

    ***if语句将列表名用在条件表达式中时，Python将在列表至少包含一个元素时返回True，为空时返回False***

    ```python
    requested_toppings = []
    if requested_toppings:
        for requested_topping in requested_toppings:
            print('adding:'+requested_topping)
        print('\nFinished making your pizza!')
    else:
        print('Are you sure you want a plain pizza?')
    ```

  * **使用多个列表**

    ```python
    requested_toppings = ['A','b','c']
    available_toppings = ['a','b','c','d','e','f','g']
    for requested_topping in requested_toppings:
        if requested_topping in available_toppings:
            print('adding:'+requested_topping)
        else:
            print('Sorry,we don\'t have '+requested_topping)
    print('\nFinished making your pizza!')
    ```



## 5 字典

  				*-----将相关信息关联，是一系列键-值对。*

```python
alien_0 = {'color':'green','point':5}
print(alien_0['point'])
```

* **添加键值对**

  ```python
  alien_0['x_position'] = 0
  alien_0['y_position'] = 25
  print(alien_0)
  ```

* **修改字典中的值**

  ````python
  alien_0['color'] = 'red'
  ````

* **删除键值对**

  ```python
  del alien_0['speed'] #指定字典名和要删除的键
  ```

* **由类似对象组成的字典**

  ```python
  favorite_languages = {
      'zhang san':'c',
      'li si':'python',
      'wang mazi':'java'
  }
  ```

* **遍历字典**

  * **遍历所有键-值对** `.items() #键-值对返回顺序与存储顺序不同` 

    ```python
    for name,language in favorite_languages.items(): #两变量存储键和值；.items()返回键-值对列表
        print(name.title() + "favorite language is " + language)
    ```

  * **遍历所有键** `.keys()`

    ```python
    for name in favorite_languages.keys():
        print(name.title())
    ```

  * **遍历所有值** `.values()` 

    * 不考虑重复项

    ```python
    for language in favorite_languages.values():
        print(language.title())
    ```

    * 考虑重复项 `set()` *#键-值对返回顺序与存储顺序不同*

    ```python
    for language in set(favorite_languages.values()):
        print(language.title())
    ```

* **嵌套**

  ​		*------列表中嵌套字典；字典中嵌套列表；字典中嵌套字典。*

  * **字典列表---在列表中存储字典** *---管理成群结队的外星人*

    ```python
    alien_0 = {'color':'red','point':'5'}
    alien_1 = {'color':'green','point':'10'}
    alien_2 = {'color':'black','point':'15'}
    aliens = [alien_0,alien_1,alien_2]
    ```

    ```python
    aliens = []
    for aliens_number in range(30):
        new_alien = {'color':'red','point':'5','speed':'medium'}
        aliens.append(new_alien)
    for alien in aliens[:3]:
        print(alien)
    print(len(aliens))
    ```

  * **在字典中存储列表** *---在字典中将一个键关联到多个值*

    ```python
    favorite_languages = {
        'zhang san':['c','c++'],
        'li si':['java','python'],
        'wang mazi':['c#']
    }
    for name,languages in favorite_languages.items():
        if len(languages) == 1:
            print('\n' + name.title() + '\'s favorite language are:'+languages[0])
        else:
            print('\n'+name.title()+'\'s favorite language are:')
            for language in languages:
                print(language)
    ```

  * **在字典中存储字典** *---多个网站用户，用户名作为键，每位用户信息作为字典*

    **注意：每位用户的字典结构都相同**

    ```python
    users = {
        'zhangsan':{
            'first':'san',
            'last':'zhang',
            'location':'china'
        },
        'lisi':{
            'first':'si',
            'last':'li',
            'location':'japan'
        }
    }
    for username,userinfo in users.items():
        print('\nusername: '+username)
        full_name = userinfo['last'] +' ' + userinfo['first']
        location = userinfo['location']
        print('Full name: '+full_name)
        print('Location: '+location)
    ```

    ​

## 6 用户输入与while循环

```python
age = input('How old are you?')
age = int(age) #强制转换为数值
if age >18:
    print('pay')
```

```python
prompt = '\nrepeat:'
prompt += '\nEnter "quit" to end the program\n'
message = ''
while message != 'quit':
    message = input(prompt)
    if message != 'quit':
        print(message)
```

* **标志---用于判断整个程序是否处于活动状态的变量。**

  ```python
  prompt = '\nrepeat:'
  prompt += '\nEnter "quit" to end the program\n'
  active = True #标志
  while active:
      message = input(prompt)
      if message == 'quit':
          active = False
      else:
          print(message)
  ```

* **break立即退出循环**

  ```python
  prompt = '\nEnter the name of a city you have insited:'
  prompt += '\nEnter "quit" to end the program\n'
  while True:
      city = input(prompt)
      if city == 'quit':
          break
      else:
          print(city)
  ```

* **continue返回到循环开头，根据条件测试结果决定是否继续执行循环**

  ```python
  number = 0
  while number <10 :
      number+=1
      if number%2==0:
          continue
      print(number)
  ```

* **使用while循环处理列表和字典**

  * **在列表中移动元素**

    ```python
    unconfirmed_users = ['a','b','c']
    confirmed_users=[]
    while unconfirmed_users: #为空时停止循环
        current_users = unconfirmed_users.pop()
        print('Verifying user: '+current_users)
        confirmed_users.append(current_users)
    print('\nThe following users have been confirmed:')
    for confirmed_user in confirmed_users:
        print(confirmed_user)
    ```

  * **删除包含特定值的所有列表元素**

    ```python
    pets = ['dog','cat','x','habbit','parrot','x','cat','x']
    print(pets)
    while 'x' in pets:
        pets.remove('x')
    print(pets)
    ```

  * **使用用户输入来填充字典**

    ```python
    responses = {}
    active = True
    while active:
        name = input('your name: ')
        response = input('your response: ')
        responses[name] = response

        repeat = input('another people respond?(yes/no)')
        if repeat == 'no':
            active = False
    print('\n---Pool Result---')
    for name,response in responses.items():
        print(name+'\'s response: '+response)
    ```




## 7 函数

* **定义函数**

  ```python
  def greet_user(username):  #定义函数 username是形参---函数完成其工作所需的一项信息
      """显示简单问候语"""  #文档字符串（注释）
      print("hello "+username)
  greet_user('wang cai')  #调用函数 'wang cai'是实参---调用函数时传递给函数的信息
  ```

* **传递实参** *---调用函数时，Python必须将函数调用中每个实参都关联到函数定义中的每个形参*

  * **位置实参** *---基于实参顺序*

  * **关键字实参** *---是传递给函数的名称-值对，在实参中将名称和值关联起来* 

    ```python
    greet_user(username = 'wang cai')
    ```

  * **默认值** *---编写函数时，给每个形参指定默认值*

    ```python
    def discribe_pet(pet_name,animal_type='dog'):
        """显示宠物信息"""
        print(pet_name,animal_type)
    discribe_pet('wang cai')
    ```

    ***注意：使用默认值时，在形参列表中必须先列出没有默认值的形参，再列出有默认值的形参***

* **返回值**

  * **简单返回值**

  	 **让实参变成可选的**	

    ```python
    def get_formmated_name(first_name,last_name,middle_name=''):
      """返回整洁的姓名"""
      if middle_name:
          full_name = first_name + ' ' + middle_name + ' ' + last_name
      else:
          full_name = first_name + ' ' + last_name
      return  full_name.title()
    name = get_formmated_name('wang','cai')
    print(name)
    name = get_formmated_name('wang','zi','ma')
    print(name)
    ```

  * **返回字典**

    ```python
    def build_person(first_name,last_name,age=''):
        """返回一个字典，包含人的信息"""
        person = {'first':first_name,'last':last_name}
        if age:
            person['age'] = age
        return person
    musician = build_person('wang','cai',22)
    print(musician)
    ```

* **传递列表**

  ```python
  def greet_users(names):
      for name in names:
          print('hello '+name)
  names = ['zhangsan','lisi','wangmazi']
  greet_users(names)
  ```

  * **在函数中修改列表** *---在函数中对这个列表所做的任何修改都是永久性的*

    ```python
    def print_model(unprinted_designs,completed_models):
        while unprinted_designs:
            current_design = unprinted_designs.pop()
            print('print model: '+current_design)
            completed_models.append(current_design)
    def show_model(completed_models):
        for completed_model in completed_models:
            print(completed_model)
    unprinted_designs = ['a','b','c','d','e'] 
    completed_models = []
    print_model(unprinted_designs,completed_models) ①
    show_model(completed_models)
    ```

  * **禁止函数修改列表** *---切片表示法创建列表副本（有充分的理由时采用，否则传原始列表）*

    ```python
    上述①中修改为 print_model(unprinted_designs[:],completed_models)
    ```

  <u>练习:对一个魔术师列表修改，每个魔术师名字前加'The Great'</u>

    ```python
  def make_greet(magicians):
      for value in range(len(magicians)):
          magicians[value]= 'The Great '+magicians[value]
  def show_magicians(magicians):
      for magician in magicians:
          print(magician)

  magicians = ['a','b','c','d','e']
  make_greet(magicians)
  show_magicians(magicians)
    ```

* **传递任意数量的实参** 

  * **结合使用位置实参和任意数量实参(*）**

    ```python
    def make_pizza(size,*toppings): #形参中*让Python创建一个名为topping的空元组，收到值都封装其中
        #"""打印顾客点的所有配料"""
        print('make a '+str(size)+'inch with the following toppings:')
        for topping in toppings:
            print('-'+topping)
            
    make_pizza(15,'a')
            make_pizza(10,'a','c','x')
    ```

      ***注意：函数接受不同类型实参，必须在函数定义中将接纳任意数量实参的形参放在最后***

  * **使用任意数量的关键字实参 (\**) **

    ```python
    def build_profile(first,last,**user_info):
        profile = {}
        profile['first'] = first
        profile['last'] = last
        for key,value in user_info.items():
            profile[key] = value
        return profile
    user_profile = build_profile('wang','cai',
                                 age='22',
                                 location='beijing')
    print(user_profile)
    ```

* **将函数存储在模块中**

  `import`语句允许在当前运行的程序文件中使用模块中的代码

  * **导入整个模块**		***调用时 `module_name.function`***

    ```python
    import pizza
    pizza.make_pizza(20,'cong','jiang','suan')
    ```

  	 **导入特定的函数** 	***调用时直接调用函数 `function`***

    ```python
    from module_name import function_name
    或from module_name import function_0,function_1,function_2
    ```

  * **使用as给模块指定别名** 

    ```python
    import module_name as mn
    ```

  * **使用as给函数指定别名** *(导入函数名称与程序现有名称冲突或函数名称太长)*

    ```python
    from module_name import function_name as fn
    ```

  * **导入模块中所有函数** *(调用时直接用函数名)* **尽量别使用，有可能函数名称相同**


## 8 类

* **创建和使用类**

  ```python
  class Dog():
      """狗类"""
      def __init__(self,name,age): #类中的函数称为方法，通过实例访问的变量称属性
          """初始化狗的名字和年龄"""
          self.name = name
          self.age = age
      def sit(self):
          """蹲下"""
          print(self.name.title()+' is now sitting.')
      def roll_over(self):
          """打滚"""
          print(self.name.title()+' rolled over.')

  my_dog = Dog('wang cai',5)
  print('my dog name:'+my_dog.name.title()+
        ', my dog age:'+str(my_dog.age))
  my_dog.sit()
  my_dog.roll_over()
  ```

* **使用类和实例**

  * **给属性指定默认值  *（`__init__()`中指定，无需提供形参）***

    ```python
    class Car():
        def __init__(self,make,model,year):
            self.make = make
            self.model = model
            self.year = year
            self.odometer_reading = 0
        def descriptive_name(self):
            long_name = str(self.year)+' '+self.make+' '+self.model
            return long_name.title()
        def read_odometer(self):
            print('This car has '+ str(self.odometer_reading)+ ' miles on it.')
        def fill_gas_tank(self):
            print('fill gas tank.')

    my_car = Car('audi','a6',2018)
    print(my_car.descriptive_name())
    my_car.read_odometer()
    ```

  * **修改属性的值**

    * 通过实例直接修改

      ```python
      my_car.odometer_reading = 66
      ```

    * 通过方法修改

      ```python
      def update_odometer(self,mileage):
          """设置里程表数值"""
          self.odometer_reading = mileage
      
      my_car.update_odometer(66)
      ```

    * 通过方法对属性值递增

      ```python
      def increment_odometer(self,miles):
          """增加里程表数值"""
          self.odometer_reading += miles
          
      my_car.increment_odometer(66)
      ```

* **继承**

  * **子类的方法`__init__()`**

    **创建子类的实例时，Python首先要给父类的所有属性赋值**

  * **给子类定义属性和方法**

    ```python
    class ElectricCar(Car):
        """电动车类"""
        def __init__(self,make,model,year):
            """初始化父类属性"""
            super().__init__(make,model,year)
            self.bettery_size = 70
        def describe_battery(self):
            print('battery size: ' + str(self.bettery_size))

    my_car = ElectricCar('tesla','model s',2016)
    my_car.describe_battery()
    ```

  * **重写父类方法**

    ```python
    def fill_gas_tank(self):
        print('electric car doesn\'t need a ggas tank.')
    ```

  * **将实例用作属性**

    ```python
    class Battery():
        def __init__(self,battery_size=70):
            self.battery_size = battery_size
        def describe_battery(self):
            print('battery size: ' + str(self.battery_size) + 'kWh battery.')
            
    class ElectricCar(Car):
        """电动车类"""
        def __init__(self,make,model,year):
            """初始化父类属性"""
            super().__init__(make,model,year)
            self.battery = Battery() #将实例用作属性
    #调用时在实例my_car中查找属性battery，并对存储在该属性中的Battery()实例调用方法      
    my_car.battery.describe_battery()
    ```

* **`isinstance()`判断类型**

  ```
  isinstance(my_car,Car)
  ```

* **`type()`获取变量类型，返回Type对象**

* **导入类**

  * **导入单个类**

    ```python
    from car import Car
    ```

  * **从一个模块中导入多个类**

    ```python
    from car import Car,ElectricCar,Battery
    ```

  * **导入整个模块**     ***调用时 `module_name.class_name`访问需要的类***

    ```python
    import car
    ```

  * **导入模块中所有类** `from car import *` ***不推荐，可能名称冲突***

  * **在一个模块中导入另一个模块**

  ​

* **Python标准库---一组模块**

  * **模块collections中的一个类OrderedDict**

    ```python
    from collections import OrderedDict
    favorate_languages = OrderedDict()
    favorate_languages['a'] = 'python'
    favorate_languages['b'] = 'c'
    favorate_languages['c'] = ['c++','java']
    favorate_languages['d'] = 'python'
    for name,language in favorate_languages.items():
        print(name.title()+'\'s favvorate language: '+ str(language))
    ```

  * **模块random包含各种方式生成随机数的函数**

    ```python
    randint(1,6) #返回1~6内的整数（包括1,6）
    ```

    ​

## 9 文件和异常

* **从文件中读取数据**

  * **读取整个文件** `.read()`

    ```python
    with open('pi_digits.txt') as file_object:
        contents = file_object.read()
        print(contents)
    ```

    `with`在不需要访问文件后将其关闭

    `open()`接受一个参数，在当前执行文件的目录下查找，返回一个表示文件的对象

    `.read()`方法读取文件全部内容将其作为字符串存储在contens中。其到达文件末尾时返回一个空字符串，这个空字符串显示为空行。可用`rstrip()`删除

    * 相对路径

      ```python
      with open('text_file\pi_digits.txt') as file_object:
      ```

    * 绝对路径

      ```python
      with open(r'F:PycharmProjects\test\text_file\pi_digits.txt') as f_o:
      ```

  * **逐行读取** `for`

    ```python
    filename = 'text_file\pi_digits.txt'
    with open(filename) as file_object:
        for line in file_object:
            print(line) #空白行原因，文件每行末尾换行符和print语句
    ```

  * **创建一个包含文件各行内容的列表**`.readline()` ***(由于open返回的文件对象只能在with代码块中使用)***

    ```python
    filename = 'text_file\pi_digits.txt'
    with open(filename) as file_object:
        lines = file_object.readlines() #readlines()从文件中读取每一行，存储在一								   #个列表中
    ```

  * **使用文件内容**

    ```python
    pi_string = ''
    for line in lines:
        pi_string += line.strip()
    print(pi_string[:12]) #小数点后10位
    print(len(pi_string))
    birthday = input('Enter your birthday: ')
    if birthday in pi_string:
        print('good luck.')
    else:
        print('meiyou')
    ```

    * 替换字符串中特定单词 `replace()` **不改变原有字符串**

      ```python
      msg = "I really like dogs."
      print(msg.replace('dog','cat'))
      ```

* **写入文件**

  * **写入空文件**

    `'r'` 读取模式

    `'w'` 写入模式

    `'a'` 附加模式

    `'r+'` 读写模式

    ````python
    filename = 'text_file/test.txt'
    with open(filename,'w') as file_object:
        file_object.write('hello')
    ````

  * **写入多行** ***---加换行符***

    ```python
    filename = 'text_file/test.txt'
    with open(filename,'w') as file_object:
        file_object.write('hello\n')
        file_object.write('world')
    ```

  * **附加到文件** ***---给文件添加内容，不覆盖***

    ```python
    filename = 'text_file/test.txt'
    with open(filename,'a') as file_object:
        file_object.write('hello\n')
        file_object.write('world')
    ```

* **异常**

  * **使用`try-except-else`代码块（当你认为可能发生异常时编写）避免崩溃**

    * `ZeroDivisionError`异常

    ```python
    print('Enter two numbers:')
    print('Enter "q" to quit.')

    while True:
        first_number = input('first number: ')
        if first_number == 'q':
            break
        last_name = input('last name: ')
        if last_name == 'q':
            break
        try:
            answer = int(first_number)/int(last_name)
        except ZeroDivisionError:
            print('bu neng bei 0 chu')
        else:
            print(answer)
    ```

    * `FileNotFoundError`异常

    ```python
    filename= 'alice.txt'
    try:
        with open(filename) as file_object:
            contents = file_object.read()
    except FileNotFoundError:
        print('mei you ci wen jian.')
    else:
        print(contents)
    ```

  * **分析文本**

     ***`.split()`以空格为分隔符将字符串拆分成多个部分***

    ***`.count()`确定特定单词在字符串中出现多少次***

    ```python
  filename = 'text_file/alice.txt'
  try:
      with open(filename) as file_object:
          contents = file_object.read()
  except FileNotFoundError:
  	print('mei you ci wen jian.') #替换
  else:
  	words = contents.split()
      print(len(words))
      print(contents.lower().count('women'))
    ```

  * **使用多个文件**

    ```python
    def count_words(filename):
        """计算一个文件包含几个单词"""
        ……
    
        filenames = ['text_file/alice.txt','text_file/siddhartha.txt','text_file/moby_dick.txt','text_file/little_women.txt']
        for filename in filenames:
            count_words(filename)
    ```

  * **失败时一声不吭**

    ```python
    except FileNotFoundError:
    	pass
    ```

    ***出现异常时什么都不会发生，pass语句还充当了占位符，提醒在程序某个地方什么都没做，并且以后可能在这里做些什么***

    ​

* **存储数据**

  ***模块json能够将简单的Python数据结构转储到文件中，并在程序再次运行时加载该文件中的数据***

  * **`json.dump()`接受两个实参：要存储的数据和可用于存储数据的文件对象**

    ```python
    import json

    filename = 'text_file/user.json'
    user_name = input('Enter your name: ')
    with open(filename,'w') as file_obj:
        json.dump(user_name,file_obj)
    ```

  * **`json.load()`**

    ```python
    import json

    filename = 'text_file/user.json'
    with open(filename) as file_obj:
        user_name = json.load(file_obj)
    print(user_name)
    ```

  * **结合**

    ```python
    import json

    filename = 'text_file/user.json'
    try:
        with open(filename) as file_obj:
            user_name = json.load(file_obj)
    except FileNotFoundError:
        user_name = input('Enter your name: ')
        with open(filename,'a') as file_obj:
            json.dump(user_name,file_obj)
            print('We will remember you when you come back. '+user_name)
    else:
        print('Hello '+user_name)
    ```

* **重构** ***---将代码划分为一系列完成具体工作的函数的过程***

  ```python
  import json

  def get_stored_username():
      """如果存储了 获取"""
      filename = 'text_file/user.json'
      try:
          with open(filename) as file_obj:
              username = json.load(file_obj)
      except FileNotFoundError:
          return None
      else:
          return username

  def get_new_username():
      username = input('Enter your name: ')
      filename = 'text_file/user.json'
      with open(filename,'w') as file_obj:
          json.dump(username,file_obj)
          return username

  def greet_user():
      username = get_stored_username()
      if username:
          print('Hello '+username)
          else:
              username = get_new_username()
              print('We will remember your name '+username)

  greet_user()
  ```



## 10 测试代码

* **单元测试和测试用例**

  单元测试：用于核实函数的某个方面没有问题

  测试用例：是一组单元测试，做这些单元测试一起核实函数在各种情况下的行为都符合要求

  全覆盖式测试：用例包含一整套单元测试，涵盖了各种可能的函数使用方式

  ```python
  import unittest #导入模块，提供了代码测试工具
  from user_last import get_formatted_name

  class NamesTestCase(unittest.TestCase): #建一个类，包含对函数的一系列单元测试

      def testfirst_last_name(self): # test开头才能自动运行
          full_name = get_formatted_name('wang','cai')
          self.assertEqual(full_name,'wang cai') #断言方法，核实得到的结果和期望结果是否一致

          unittest.main() #Python运行这个文件中的测试
  ```

* **测试类**

  ```python
  class AnonymousSurvey():
      def __init__(self,question):
          self.question = question
          self.responses = []
      def show_question(self):
          print(self.question)
      def store_response(self,new_response):
          self.responses.append(new_response)
      def show_result(self):
          print('Survey results:')
          for response in self.responses:
              print('-'+ response)
  ```

  ```python
  import unittest
  from survey import AnonymousSurvey
  
  class TestAnonymousSurvey(unittest.TestCase):
      def test_store_response(self):
          question = 'favorate language:'
          my_survey = AnonymousSurvey(question)
          responses = ['python','c','java']
          for response in responses:
              my_survey.store_response(response)
          for response in responses:
              self.assertIn(response,my_survey.responses)
  
  unittest.main()
  ```

  * **方法setUp()**

    ```python
    import unittest
    from survey import AnonymousSurvey

    class TestAnonymousSurvey(unittest.TestCase):

        def setUp(self):
            """创建一个调查对象和一组答案，供使用的测试方法使用"""
            question = 'favorate language:'
            self.my_survey = AnonymousSurvey(question)
            self.responses = ['python', 'c', 'java']
            def test_store_response(self):
                for response in self.responses:
                    self.my_survey.store_response(response)
                for response in self.responses:
                    self.assertIn(response,self.my_survey.responses)

        unittest.main()
    ```

  * ```python
    class Employee():
        def __init__(self,name,age,money):
            self.name = name
            self.age = age
            self.money = money
    
        def give_raise(self,increase=5000):
            self.money+=increase
            import unittest
            from Employee import Employee
    
    class EmployeeTestCase(unittest.TestCase):
        def setUp(self):
            self.e = Employee('wangcai',12,5000)
        def test_give_default_raise(self):
            self.e.give_raise()
            self.assertEqual(self.e.money,10000)
        def test_give_custom_raise(self):
            self.e.give_raise(10000)
            self.assertEqual(self.e.money,15000)
            unittest.main()     
    
    ```




## 11 函数式编程

​						***------functional，一种编程范式***

