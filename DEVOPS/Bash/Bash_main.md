# Create file

``` create_file
$ nano myscript.sh
```

```file_myscript.sh
#! /bin/bash
```

``` RUN_bash_script_in_term
sudo chmod a+x myscript.sh
./myscript

or

bash ./myscript.sh
```

# Other commands

``` output_text
echo "hello world"
```

``` open_new_terminal_and_continue
xterm &
```

``` variable
myOs=`u name -a`
```

``` output_variable
num1=45
num2=54
summa = $((num1+num2))
echo="$num1 + $num2 = $summa"
```

```
myhost=`hostname`          /hostname - IP нашей машины
mygtw="8.8.8.8"            /8.8.8.8 - dns address google

ping -c 4 $myhost
ping -c 4 $mygtw
```

# Lesson 2

## if and case

``` else_if
if [ "$1" == "Baracuda" ]; then
	echo "Hello $1"
elif ["$1" == "Trump" ]; then
	echo "Hello $1"
else echo "Hello $1"
fi

			/$1 - первый вводимый параметр с терминала
```

``` case
x = $2

case $x in
	1) echo "hello one";;
	[2-9]) echo "hello newfag";;
	"Hello") echo "hello-hello?"
	*) echo "error"
esac

			/$2 - первый вводимый параметр с терминала
```

## Циклы

``` while
COUNTER=0
while [ $COUNTER -lt 10 ]; do
echo "Value Counter is $COUNTER"
# let COUNTER=COUNTER+1
# let COUNTER+=1
done
```

``` for_range
for x in [1..10]; do 
echo "X = $x"
done
```

``` for_classic
for (( i=0; i<=10; i++ )); do
echo "Value I = $i"
done
```

``` for_bladstvo
for myfile in `ls *.txt`; do
cat $myfile
done
				#`ls *.txt` - выберет все файлы с расширением txt
				# они поочередно запишутся в переменную myfile
				# и будет выполнена команда cat для каждого этого файла
```

## functions
``` function_setting_and_return
#! /bin/bash

summa = 0     #return в bash_scripts не существует. Для возврата переменной
              #из функции создаем глобальную переменную $summa
function () 
{
	echo "num1 = $1"
	echo "num2 = $2"
	$summa=$(($1+$2))
}

function 20 30     #передача параметров в функцию через пробел
echo "Summa = $summa"

```

