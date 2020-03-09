# JavaScript

1. Zmienne

*var*, od 2015 dochodzą *let* i *const*

let p = 10;
let q = "JavaScript";
let r = true;

Od EcmaScript6+ różnica między *var* a *let* polega na różnym zasięgu działania zadeklarowanej zmiennej. Konstrukcja *var* działa w kontekście funkcji, a *let* w kontekście bloku kodu w funkcji. Przy *var* występuje tzw. *hoisting*. 

*Hoisting* w JavaScripcie oznacza przeniesienie deklaracji na samą górę (do globalnego zasięgu lub do zasięgu funkcji). **Funkcje lub zmienne mogę być deklarowane po ich użyciu.**

Natomiast *const* to wartość stałej i nie może zostać zmieniona poprzez ponowne przypisanie; stała nie może także być ponownie zadeklarowana.

Przykład 1. VAR

(function () {
  var letter = 'A';  
  if (letter.length) {
    console.log(letter); // zwraca nam A
    var letter = 'B';
    console.log(letter); // zwraca nam B
  }  
  console.log(letter); // zwraca nam B
})();

Przykład 2. LET

(function () {
  let letter = 'A';  
  if (letter.length) {
    console.log(letter); // zwraca undefined
    let letter = 'B';
    console.log(letter); // zwraca B
  }  
  console.log(letter); // zwraca A
})();

JavaScript ma tylko jeden typ liczbowy. Wewnętrznie jest on reprezentowany jako 64-bitowa liczba zmiennoprzecinkowa, tak samo jak typ *double* w Javie. 

Nie ma osobnego typu dla liczb całkowitych. Z tego powodu 1 i 1.0 mają tę samą wartość. Jest to bardzo wygodne, bo nie pojawiają się problemy przepełnienia krótkich typów całkowitych, a wszystko, co trzeba wiedzieć o liczbie, to po prostu to, że jest to liczba.

Nazwy zmiennych nie mogą zawierać spacji, cyfr na początku i być słowami:
- abstract
- boolean 
- break 
- byte
- case 
- catch 
- char 
- class 
- const 
- continue
- debugger 
- default 
- delete 
- do 
- double
- else 
- enum 
- export 
- extends
- false 
- final 
- finally 
- float 
- for 
- function
- goto
- if 
- implements 
- import 
- in 
- instanceof 
- int 
- interface
- long
- native 
- new 
- null
- package 
- private 
- protected 
- public
- return
- short 
- static 
- super 
- switch 
- synchronized
- this 
- throw 
- throws 
- transient 
- true 
- try 
- typeof
- var 
- volatile 
- void
- while 
- with

2. Funkcje

function mojaFunkcja(p,q) {
  let r = p + q;
  return r;
};
let s = r(2,4);
alert(s);

3. Instrukcje warunkowe

let price = 300;
if ( price > 300 ) {
  alert("Bezpłatna wysyłka");
} else {
  alert("Dodaj produkty za min. 300 zł, by uzyskać bezpłatną wysyłkę");
};

4. Iteracja na przykładzie pętli *while* i *for*

let i = 1;
while ( i <= 10 ) {
  alert(i);
  i++;
};

--

for( let i = 1; i<= 10; i++ ) {
  alert(i);
};

5. Tablice

Zbiór różnych wartości, np, lista nazw użytkowników.
Wartości przechowujemy w nawiasach kwadratowych, oddzielając je przecinkiem. Można łączyć wartości różnego typu.
JS nie posiada "prawdzwiwych" tablic, jednak te które w nim istnieją, są bardzo łatwe w użyciu. Nie ma np. konieczności deklarowania ich rozmiaru i nie występują błędy przepełnienia tablicy.

*let numbersArray = [0,1,2,3,4,5,6,7,8,9];*
*let numbersArray = ["user1","user2","user3"];*
*let numbersArray = ["user1",1,"user2",2];*

Tablice posiadają swój indeks, numerację elementów. 
Wywołanie całej tablicy i (pierwszej) wartości z tablicy.

*alert(numbersArray);*
*alert(numbersArray[0]);*

for( let i = 0, i < numbersArray.length, i++ ) {
  alert(numbersArray[i]);
};

6. Obiekty

Obiekty można traktować jako pewne całości, np. selektor typu *button*. Ma właściwości określające jego zawartość (np. tekst), szerokość, wysokość, pozycję na stronie. Ale też ma metody, czyli funkcje które może wykonać - np. *focus* czy *blur*, które go zaznaczą lub odznaczą gdy zostaną odpalane. 

Przykład obiektu-psa:

const dog = {
    name: "Szarik",
    speed: 1000,
    showText: function() {
        return "Jeżdżę czołgiem";
    }
}

Do właściwości i metod obiektu możemy się odwoływać na dwa sposoby:

- sposób 1:

dog.name; 
dog.speed; 
dog.showText(); 

- sposób 2:

dog["name"]; 
dog["speed"]; 
dog["showText"]();

Obiekty wbudowane (w JS):
- Number
- Math
- String
- Date
- RegExp

Obiekt *Date*:

var today = new Date();
today.getDay();
today.getMonth();

Obiekt *Math*:

Wbudowany obiekt zawierający własności i metody związane z funkcjami i stałymi matematycznymi. Na przykład własność *PI* obiektu *Math* zawiera wartość liczby pi.

var howMuchIsPi = Math.PI;

Obiekt *String*:

charAt() 	            Returns the character at the specified index.
charCodeAt() 	        Returns the Unicode of the character at the specified index.
concat() 	            Joins two or more strings, and returns a new string.
endsWith() 	            Checks whether a string ends with a specified substring.
fromCharCode() 	        Converts Unicode values to characters.
includes() 	            Checks whether a string contains the specified substring.
indexOf()               Returns the index of the first occurrence of the specified value in a string.
lastIndexOf() 	        Returns the index of the last occurrence of the specified value in a string.
localeCompare()         Compares two strings in the current locale.
match() 	            Matches a string against a regular expression, and returns an array of all matches.
repeat() 	            Returns a new string which contains the specified number of copies of the original string.
replace()               Replaces the occurrences of a string or pattern inside a string with another string, and return a new string without modifying the original string.
search() 	            Searches a string against a regular expression, and returns the index of the first match.
slice()                 Extracts a portion of a string and returns it as a new string.
split()                 Splits a string into an array of substrings.
startsWith() 	        Checks whether a string begins with a specified substring.
substr() 	            Extracts the part of a string between the start index and a number of characters after it.
substring()             Extracts the part of a string between the start and end indexes.
toLocaleLowerCase()     Converts a string to lowercase letters, according to host machine's current locale.
toLocaleUpperCase() 	Converts a string to uppercase letters, according to host machine's current locale.
toLowerCase()           Converts a string to lowercase letters.
toString()              Returns a string representing the specified object.
toUpperCase()           Converts a string to uppercase letters.
trim()                  Removes whitespace from both ends of a string.
valueOf()               Returns the primitive value of a String object.
