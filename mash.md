# Լաբորատոր աշխատանք 1
###  1. Ստեղծել lab1 անունով դիրեկտորիա, որում ստեղծել 4 տեքստային ֆայլ՝ file.txt, file1.txt, file2.txt, file3.txt և 2 դիրեկտորիա՝ dir1, dir2։

* Ստեղծում ենք lab1 դիրեկտորիա
```
 mkdir lab1
```
* Ստեղծում ենք .txt 4 ֆայլ: Նշենք, որ Ֆայլերի անվանումները Case Sensitive են:
```
touch file.txt file1.txt file2.txt file3.txt
``` 
* Ստեղծում ենք dir1 և dir2 դիրեկտորիաներ
```
mkdir dir1 dir2
```
### 2. Կատարել հետևյալ հրամանները և բացատրել տարբերությունը․ ls *.txt և ls * .txt
```
ls *.txt 
```
որոնեց տվյալ դիրեկտորիայի բոլոր այն ֆայլերը, որոնք վերջանում են .txt-ով
```
ls * .txt
```
որոնեց բոլոր այն ֆայլերը, որոնք վերջանում են .txt-ով

### 3. Ցուցադրել բոլոր տեքստային ֆայլերը (ավարտվում է .txt սիմվոլներով), որոնց անվանումը սկսվում է f սիմվոլով և բաղկացած է 4 սիմվոլից։
```
ls -1 f???.txt
```
```-1``` Գրում ենք նրա համար, որ նոր տողից տպի

### 4.Ցուցադրել բոլոր տեքստային ֆայլերը, որոնց անվանումը սկսվում է file բառով, որին հաջորդում է թվանշան։
```
ls -1 file*[[:digit:]]*.txt
```
```[[:digit:]]``` Համապատասխանում է (0-9) որևէ թվանշանի

### 5. Ցուցադրել բոլոր տեքստային ֆայլերը, որոնց անվան վերջին սիմվոլը փոքրատառ է, կամ 1, 2 թվանշաններից որևէ մեկը։
```
ls -1 *([[:lower:]])|([1-2]).txt
```
```[[:lower:]]``` սիմվոլը փոքրատառ է

### 6. Պատճենել /etc/passwd ֆայլը lab1 դիրեկտորիայում
```
cp/etc/passwd lab1
```
```cp``` հրամանը պատճենում է ֆայլը

### 7. Անվանափոխել պատճենված ֆայլը՝ այն դարձնելով new: Տեղափոխել new ֆայլը դեպի dir1, այնուհետև տեղափոխել դեպի dir2:
```
mv lab1 new
mv new dir1
mv new dir2
```
```mv``` (move) հրամանը վերանվանում կամ տեղափոխում է ֆայլը։

### 8. Անվանափոխել dir2-ը՝ այն դարձնելով dir3։ Տեղափոխել dir3-ը դեպի dir1։
```
mv dir2 dir3
mv dir3/* dir1/
```

### 9. Տեղափոխել dir3-ում գտնվող new ֆայլը դեպի lab1։
```
mv ./dir1/new ./
```

### 10. Ջնջել lab1 դիրեկտորիան։
```
rm -r lab1
```

# Լաբորատոր աշխատանք 2

### 1. Կատարել հետևյալ հրամանները, բացատրել տարբերությունը․ 1. cat > file1 2. cat file1 3. cat < file1

```cat```  (concatenate) հրամանը կարդում է մեկ կամ մի քանի ֆայլեր և արտածում է դրանց պարունակությունը։

```bash
cat > file1
```
Այս հրամանը ստեղծում կամ վերագրանցում է ```file1 ```անունով ֆայլ և թույլ է տալիս տեքստ մուտքագրել այդ ֆայլի մեջ: Կարող ենք մուտքագրել տեքստ, սեղմել ```Ctrl+D``` (մուտքագրումն ավարտելու համար) և բովանդակությունը պահել ֆայլում:
```bash
cat file1
```
Այս հրամանը ցուցադրում է ```file1``` ֆայլի բովանդակությունը տերմինալի մեջ: Այսպիսով, եթե ```file1``` գոյություն ունի և պարունակում է որոշակի տեքստ, ապա կտեսնենք այդ տեքստը էկրանին:
```bash
cat < file1
```
Այս հրամանը օգտագործում է ```<``` նիշը` մուտքագրումը վերահղելու համար: Այսինքն, cat հրամանը կարդում է ```file1``` ֆայլի մուտքագրումը և ցուցադրում այն ​​տերմինալի էկրանին: Սա համարժեք է ```cat file1``` հրամանին:

### 2. Ստեղծել որոշակի պարունակությամբ 3 տեքստային ֆայլ՝ file1.txt, file2.txt, file3.txt։ Այս ֆայլերի պարունակությունը կցել միմյանց և գրել նոր ֆայլում՝ final.txt։
```bash
cat > file1.txt
cat > file2.txt
cat > file3.txt
cat file1.txt file2.txt file3.txt > Final.txt
```

### 3. Ցուցադրել /home/student դիրեկտորիայում տեքստային ֆայլերի քանակը։

```bash
ls -l /home/student/*.txt | wc -l
```

### 4. Սորտավորել file1.txt, file2.txt, file3.txt ֆայլերի պարունակությունը և գրել նոր ֆայլում։

```bash
cat file1.txt file2.txt file3.txt | sort > sorted.txt
```

```sort``` Սորտավորում է մեկ կամ մի քանի ֆայլերի տողերը և արդյունքը տեղադրում ```STDOUT``` հոսքում։

### 5.Արտածել /home/student դիրեկտորիայի առաջին 15 ֆայլերը՝ դասավորված նվազման կարգով ըստ ֆայլի ծավալի։

```bash
ls /home/student/* | sort -rh | head -n 15
```

```sort -rh``` Սորտավորում է նվազման կարգով ```(r) reversed order in (-h) human-readable size```


### 6. Արտածել /home/student դիրեկտորիայի ֆայլերի ցուցակը, միաժամանակ այն տեղադրելով ls.txt ֆայլում։

```bash
ls /home/student > /home/student/ls.txt
```

### 7.Օգտագործելով tr հրամանը՝ գաղտնագրել "secret text" տողը ROT13 ալգորիթմով։ Վերծանել գաղտնագրված հաղորդագրությունը։

```bash
echo "secret text" | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
Գաղտնագրված հաղորդագրությունը կլինի ```"frperg grkg"``` քանի որ 
* ```s -> f```: ```'s'``` տառը իր տեղից 13 տառ առաջ է գնում և դառնում է ```'f'```.
* ```e -> r```: ```'e'``` տառը իր տեղից 13 տառ առաջ է գնում և դառնում է ```'r'```.
* ```c -> p```: ```'c'``` տառը իր տեղից 13 տառ առաջ է գնում և դառնում է ```'p'``` 
* ```r -> e```: ```'r'``` տառը իր տեղից 13 տառ առաջ է գնում և դառնում է ```'e'```.
* ```e -> r```: ```'e'``` տառը իր տեղից 13 տառ առաջ է գնում և դառնում է ```'r'```.
* ```t -> g```: ```'t'``` տառը իր տեղից 13 տառ առաջ է գնում և դառնում է ```'g'```.
* ```x -> k```: ```'x'``` տառը իր տեղից 13 տառ առաջ է գնում և դառնում է ```'k'```. 

### 8. Ստեղծել նոր ֆայլ՝ home.txt, հետևյալ պարունակությամբ․Student’s home directory is {home_dir}.sed հրամանի միջոցով փոխարինել {home_dir} հատվածը /home/student-ով։

```bash
echo "Student’s home directory is {home_dir}." > home.txt
sed 's/{home_dir}/\/home\/student/' home.txt > home_modified.txt
```
```sed (stream editor)``` ծրագիրն օգտագործվում է տեքստում փոփոխություններ
կատարելու նպատակով։

### 9. Ստեղծել ֆայլ, որն ունի առնվազն 5 տող պարունակություն՝ file4.txt։ Արտածել 2-4-րդ տողերը:

```bash
echo "Line 1" > file4.txt
echo "Line 2" >> file4.txt
echo "Line 3" >> file4.txt
echo "Line 4" >> file4.txt
echo "Line 5" >> file4.txt
sed -n '2p;4p' file4.txt
```

### 10. Ջնջել file4.txt ֆայլի 2-4-րդ տողերը։

```bash
sed -i '2d;4d' file4_modified.txt
```

# Լաբորատոր աշխատանք 3

### 1.Ցուցադրել /etc դիրեկտորիայի բոլոր ֆայլերը, որոնց անվան մեջ թվանշան կա։

```bash
ls /etc | grep '[0-9]'
```
```grep (global regular expression print)``` հրամանը տեքստային ֆայլերում փնտրում է նշված
ռեգուլյար արտահայտությանը համապատասխանող տողերը և արտածում։

### 2. Ստեղծել որոշակի պարունակությամբ ֆայլ։ Ֆայլում փնտրել այՆ տողերը, որոնք բաղակացած են 5 տառից, և ավարտվում են lo տառերով։

```bash
echo -e "Hello\nWorld\nTestlo\nHillo\nOtherlo\n" > sample_file.txt
grep -E '\b\w{5}lo$' sample_file.txt
```
CONTENT:
```bash
Hello
World
Testlo
Hillo
Otherlo
```
```grep -E '\b\w{5}lo$' sample_file.txt```: Օգտագործում է `grep` հրամանը `sample_file.txt` Ֆայլում տողերը գտնելու համար. Մեզ պետք են այն տողերը, որոնք բաղակացած են 5 տառից, և ավարտվում են `"lo"` տառերով։`\w{5}` այսինքն 5 տառանի, և `$` նշանակում է տողի ավարտ։

EXPECTED OUTPUT:
```bash
Testlo
Otherlo
```

### 3. Ցուցադրել հետևյալ հրամանների տարբերությունը․ grep -h '[A-Z]' dirlist*.txt, grep -h '[-AZ]' dirlist*.txt, grep -h '^[A-Z]' dirlist*.txt, grep -h '[^A-Z]' dirlist*.txt:

* `grep -h '[A-Z]' dirlist*.txt`:  Որոնում է առնվազն մեկ մեծատառ պարունակող տողեր:
* `grep -h '[-AZ]' dirlist*.txt`:   Որոնում է `«-»`, `«A»` կամ `«Z»` նիշերից որևէ մեկը պարունակող տողեր:
* `grep -h '^[A-Z]' dirlist*.txt`:  Որոնում է մեծատառով սկսվող տողեր:
* `grep -h '[^A-Z]' dirlist*.txt`:  Որոնում է տողեր, որոնք պարունակում են մեծատառերից բացի որևէ այլ նիշ:

### 4. dirlist-bin.txt և dirlist-sbin.txt ֆայլերում փնտրել այն տողերը, որոնք սկսվում են bz կամ zip բառերով։

```bash
grep -E '^(bz|zip)' dirlist-bin.txt dirlist-sbin.txt
```

### 5. Ցուցադրել հետևյալ հրամանների տարբերությունը․ grep -Eh '^(bz|gz|zip)' dirlist*.txt և grep -Eh '^bz|gz|zip' dirlist*.txt

* `grep -Eh '^(bz|gz|zip)' dirlist*.txt`  Փնտրում է `«bz»`, `«gz»` կամ `«zip»` -ով սկսվող տողեր:
* `grep -Eh '^bz|gz|zip' dirlist*.txt`  Որոնում է `«bz»`-ով սկսվող կամ `«gz»` կամ `«zip»` պարունակող տողեր:

### 6. Ստուգել տրված էլ․ հասցեի վավերականությունը։ Օր․՝ test@test.com 

```bash
echo "test@test.com" | grep -E '^([a-zA-Z0-9._%+-]+)@([a-zA-Z0-9.-]+)\.([a-zA-Z]{2,})$'
```
1. `([a-zA-Z0-9._%+-]+)` `@` -ից առաջ գրվող լոկալ հատվածն է, որը պետք է պարունակի տառեր, թվեր,`.`,`_`,`%`,`+`,`-` սիմվոլներից։
2. `@` սիմվոլը
3. `Domain` կամ `@` -ից հետո գրվող հատվածը պետք է պարունակի տառեր, թվեր, `.`,`-`։
4. Հետո պետք է լինի `.` սիմվոլը և առնվազն `2` տառ։

### 7. Ստուգել տրված IPv4 հասցեի վավերականությունը։ Օր․՝ 192․168․0․1

```bash
echo "192.168.0.1" | grep -E '^([0-9]{1,3}\.){3}[0-9]{1,3}$'
```
Վավեր `IPv4` հասցեն կազմված է `4` թվից, որոնք իրարից բաժանված են `.`-ով և `0`-ից `255`-ի սահմաններում են գտնվում։

### 8. Ստեղծել որոշակի պարունակությամբ ֆայլ, որի տողերից մեկում գրել Level բառը։ Ֆայլում փնտրել այն տողերը, որոնք պարունակում են 5 տառից բաղկացած պալինդրոմներ (բառեր, որոնք 2 ուղղություններով կարդացվում են նույնաբար)։

```bash
echo -e "Level\nexample\ndeified\ntest\nradar\nanother" > example.txt
```
CONTENT:
```bash
Level
example
deified
test
radar
another
```
5 տառից բաղկացած պալինդրոմներ գտնող հրամանը
```bash
grep -E '^(.)(.)(.)\3\2\1$' example.txt
```
`(.)(.)(.)` առաջին `3` սիմվոլներն ա վերցնում, իսկ `\3\2\1` վերջին `3` սիմվոլներն ա վերցնում և համեմատում՝ նույնն են թե չէ։

EXPECTED OUTPUT:
```bash
Level
radar
```

### 9. Տրված է հետևյալ ամսաթիվը․ 01/02/1970: Ձևափոխել այն՝ բերելով հետևյալ ֆորմատի․ 1970-02-01

```bash
echo "01/02/1970" | sed -E 's~([0-9]+)/([0-9]+)/([0-9]+)~\3-\2-\1~'
```

* `([0-9]+)/([0-9]+)/([0-9]+)`: Հրամանի այս հատվածը առանձնացնում է `3` (խումբ օր, ամիս, տարի)՝ բաղկացած թվանշաններից և իրարից առանձնացված `/`-ով: 
* `\3-\2-\1`: Այս հատվածը տեղերը փոխում է և արանքում ավելացնում է `-` ։ `\3` վերաբերվում է `3`-րդ խմբին (տարի), `\2` վերաբերվում է `2`-րդ խմբին (ամիս), և `\1` վերաբերվում է առաջին խմբին (օր):

### 10. . Տրված է հետևյալ հեռախոսահամարը․ 0xx 12-34-56 Ձևափոխել այն՝ բերելով հետևյալ ֆորմատի․ (0xx) 123-456

```bash
echo "0xx 12-34-56" | sed -E 's~^(0xx) ([0-9]{2})-([0-9])([0-9])-([0-9]{2})$~(\1) \2\3-\4\5~'
```


# Լաբորատոր աշխատանք 4

### 1. Ստեղծել նոր ֆայլ՝ file.txt, և դրա համար սահմանել հետևյալ իրավունքները․ - rwx r-- r--

```bash
touch file.txt
chmod 744 file.txt
```
Ֆայլի ռեժիմը փոփոխելու համար օգտագործվում է `chmod` հրամանը

`7` = `rwx`

`4` = `r--`

### 2. Փոփոխել file.txt ֆայլի իրավունքները՝ բոլոր օգտատերերի համար ավելացնելով կատարելու իրավունք։ Օգտվել ֆայլի ռեժիմների սիմվոլիկ ներկայացումից։

```bash
chmod a+x file.txt
```

### 3. Փոփոխել file.txt ֆայլի իրավունքները՝ խմբի օգտատերերի և այլ օգտատերերի համար հեռացնելով կատարելու իրավունքը։ Օգտվել սիմվոլիկ ներկայացումից։

```bash
chmod go-x file.txt
```

`g` `(Group)` – Խմբին պատկանող օգտատերեր

`o` `(Other)` – Մնացած օգտատերեր

`-x` - հեռացնում է կատարելու իրավունքը

### 4. Փոփոխել file.txt ֆայլի իրավունքները՝ հեռացնելով բոլոր իրավունքները, և սահմանելով գրելու և կարդալու իրավունքներ միայն ֆայլի սեփականատիրոջ համար։ Նույն գործողությունը կատարել 2 անգամ ՝ օգտվելով ֆայլի ռեժիմների 8-ական և սիմվոլիկ ներկայացումներից։

```bash
chmod 600 file.txt
```
`0` = `---`

`6` = `rw-`

### 5.Ստեղծել նոր դիրեկտորիա՝ dir: Սահմանել հետևյալ իրավունքները․ d rw- rw- rw-։ dir դիրեկտորիայում ստեղծել նոր ֆայլ՝ file.txt։ Բացատրել ստացված հաղորդագրությունը։ Փոփոխել դիրեկտորիայի իրավունքներն այնպես, որ ֆայլը հաջողությամբ ստեղծվի։

```bash
mkdir -m 666 dir
cd dir
touch file.txt
```

### 6. dir դիրեկտորիայում ստեղծել ևս 2 ֆայլ՝ file1.txt, file2.txt։ Մեկ հրամանի կատարմամբ փոփոխել դիրեկտորիայի բոլոր ֆայլերի իրավունքները՝ սահմանելով - rwx rw- rw-։

```bash
touch dir/file1.txt dir/file2.txt
chmod 766 dir/*
```
### 7. umask հրամանի միջոցով սահմանել այնպիսի bitmask, որ նոր ստեղծվող ֆայլերը լռելյայն կերպով ունենան հետևյալ իրավունքները․ - rw- r-- ---

`umask` հրամանը ղեկավարում է ֆայլի ստեղծման պահին տրվող իրավունքները։ Հրամանի կատարման արդյունքում ցուցադրվում է `8`-ական `bitmask (0022)`, որը սահմանում է այն
իրավունքները, որոնք պետք է հեռացվեն ֆայլից։

```bash
umask 027
```

### 8.umask հրամանի միջոցով սահմանել այնպիսի bitmask, որ նոր ստեղծվող ֆայլերը լռելյայն կերպով ունենան հետևյալ իրավունքները․ - rw- --- ---: Վերադարձնել bitmask-ի լռելյայն արժեքը՝ կատարելով umask 0022 հրամանը։

```bash
umask 077
umask 022
```
 
### 9. Ստեղծել սկրիպտ, որը կարտածի /home/student դիրեկտորիայի ֆայլերի ցուցակը։ Սկրիպտի համար սահմանել - -wx r-- r-- իրավունքները։ Կատարել սկրիպտը և բացատրել ստացված հաղորդագրությունը։ Փոփոխել իրավունքներն այնպես, որ սկրիպտը կատարվի։

```bash
echo 'ls /home/student' > script.sh
chmod 741 script.sh
chmod +x script.sh
./script.sh
```

### 10. Սկրիպտը տեղադրել ~/bin դիրեկտորիայում։ Փոփոխել $PATH փոփոխականն այնպես, որ սկրիպտը հնարավոր լինի կատարել առանց հասցեն նշելու։

```bash
mkdir ~/bin
mv script.sh ~/bin
echo 'export PATH=$PATH:~/bin' >> ~/.bashrc
source ~/.bashrc
```

# Լաբորատոր աշխատանք 5

### 1. Ստեղծել կամայական արժեքով փոփոխական՝ str: Ցուցադրել հետևյալ հրամանների աշխատանքի արդյունքի տարբերությունը. echo$str2 և  echo ${str}2։

```bash
str="HelloWorld"
echo str2         
echo ${str}2      
```
OUTPUT:
```bash
str2
HelloWorld2
```

### 2. Արտածել հետևյալ արտահայտության արժեքը․ 5<sup>2</sup> * 4/10
```bash
echo $((5 ** 2 * 4 / 10))
```

### 3. Ցուցադրել հետևյալ հրամանների աշխատանքի արդյունքի տարբերությունը․echo "The balance for user $USER is: $5.00" և  echo "The balance for user $USER is: \$5.00"

```bash
echo "The balance for user $USER is: $5,00" 
# The balance for user root is: ,00
echo "The balance for user $USER: \$5,00"  
# The balance for user root: $5,00
```

### 4. Ցուցադրել հետևյալ հրամանների աշխատանքի արդյունքի տարբերությունը․ echo '$USER $((2 + 2)) $(ls)' և echo "$USER $((2 + 2)) $(ls)"

```bash
echo '$USER $((2 + 2)) $(ls)' 
# $USER $((2 + 2)) $(ls)
echo "$USER $((2 + 2)) $(ls)" 
# root 4 labs main.sh
```

### 5. Առանձին տողերում արտածել ընթացիկ դիրեկտորիան և այնտեղ առկա տեքստային ֆայլերի քանակը։ Օգտագործել Here document:

```bash
current_dir=$(pwd)
num_files=$(ls -l | grep -c "^-")
cat <<EOF
Current directory: $current_dir
Number of files: $num_files
EOF
```

### 6. Գրել 2 թվեր գումարող ֆունկցիա։ Թվերը ֆունկցիային փոխանցել որպես արգումենտներ։

```bash
#!/bin/bash
add_numbers() {
    local result=$(( $1 + $2 ))
    echo "The sum of $1 and $2 is: $result"
}

add_numbers 5 7
```
OUTPUT:
```bash
12
```

### 7. Գրել ֆունկցիա, որը որպես արգումենտ կստանա դիրեկտորիայի անվանումը և կարտածի այնտեղ առկա ֆայլերի քանակը։

```bash
#!/bin/bash

count_files() {
    local directory="$1"
    local file_count=$(find "$directory" -type f | wc -l)
    
    echo "The number of files in '$directory' is: $file_count"
}

count_files "/path/to/directory"
```
 For example, if you run the script with the directory `"/path/to/directory"` and there are `10` files in that directory, the output would be:
 ```bash
 The number of files in '/path/to/directory' is: 10
 ```

 ### 8. Գրել սկրիպտ, որում նոր ստեղծված ֆայլի համար ստուգել, թե արդյոք այն ունի կարդալու / գրելու / կատարելու թույլտվություն, և արտածել համապատասխան հաղորդագրություն։

 ```bash
 #!/bin/bash

filename="testfile.txt"

# Ստեղծում ենք նոր ֆայլ
touch "$filename"

# Ստուգենք արդյոք այդ ֆայլը գոյություն ունի թե ոչ
if [ -e "$filename" ]; then
    # Ստուգենք կարդալու կարողությունը
    if [ -r "$filename" ]; then
        echo "The file has read permission."
    else
        echo "The file does not have read permission."
    fi

    # Ստուգենք գրելու կարողությունը
    if [ -w "$filename" ]; then
        echo "The file has write permission."
    else
        echo "The file does not have write permission."
    fi

    # Ստուգենք արտածելու կարողությունը
    if [ -x "$filename" ]; then
        echo "The file has execute permission."
    else
        echo "The file does not have execute permission."
    fi
else
    echo "The file does not exist."
fi
 ```

### 9. Գրել սկրիպտ, որը կորոշի տրված 2 թվերից մեծագույնը և կարտածի։

```bash
#!/bin/bash

find_maximum() {
    if [ "$1" -gt "$2" ]; then
        echo "$1 is greater than $2"
    elif [ "$1" -lt "$2" ]; then
        echo "$2 is greater than $1"
    else
        echo "Both numbers are equal"
    fi
}

find_maximum 8 5
```
OUTPUT:
```bash
8 is greater than 5
```

### 10. Գրել սկրիպտ, որը կորոշի տրված թիվը զույգ է, թե կենտ։ Արտածել համապատասխան հաղորդագրություն։

```bash
#!/bin/bash

check_even_odd() {
    if [ $(( $1 % 2 )) -eq 0 ]; then
        echo "$1 is an even number."
    else
        echo "$1 is an odd number."
    fi
}

check_even_odd 7
check_even_odd 6
```
OUTPUT:
```bash
7 is an odd number.
6 is an even number.
```


# Լաբորատոր աշխատանք 6

### 1. Գրել սկրիպտ, որը տրված թվի համար կարտածի հաղորդագրություն այն մասին, արդյոք թիվը դրական է, բացասական, թե՝ 0։ Թիվը վավերացնել ռեգուլյար արտահայտության միջոցով։ Պայմանների ստուգման համար օգտագործել [[ ]] օպերատորը։

```bash
#!/bin/bash

check_number() {
    if [[ $1 =~ ^[+-]?[0-9]*\.?[0-9]+$ ]]; then
        if [ "$1" -gt 0 ]; then
            echo "$1 is a positive number."
        elif [ "$1" -lt 0 ]; then
            echo "$1 is a negative number."
        else
            echo "$1 is zero."
        fi
    else
        echo "Invalid input. Please enter a valid number."
    fi
}

check_number -3.14
```
OUTPUT:
```bash
-3.14 is a negative number.
```

### 2.Կատարել 1-ին կետը՝ պայմանների ստուգման համար օգտագործելով (( )) օպերատորը։

```bash
#!/bin/bash

check_number() {
    if (( $1 > 0 )); then
        echo "$1 is a positive number."
    elif (( $1 < 0 )); then
        echo "$1 is a negative number."
    else
        echo "$1 is zero."
    fi
}

check_number -3.14
```

### 3. Գրել սկրիպտ, որը կստուգի, թե արդյոք տրված թիվը 2-ի, 3-ի `և` 5-ի բազմապատիկ է:

```bash 
#!/bin/bash

check_multiples() {
    if (( $1 % 2 == 0 && $1 % 3 == 0 && $1 % 5 == 0 )); then
        echo "$1 is a multiple of 2, 3, and 5."
    else
        echo "$1 is not a multiple of 2, 3, and 5."
    fi
}

check_multiples 30

```
OUTPUT:
```bash 
30 is a multiple of 2, 3, and 5.
```

### 4. Գրել սկրիպտ, որը կստուգի, թե արդյոք տրված թիվը 2-ի, 3-ի `կամ` 5-ի բազմապատիկ է:

```bash
#!/bin/bash

check_multiples() {
    if (( $1 % 2 == 0 || $1 % 3 == 0 || $1 % 5 == 0 )); then
        echo "$1 is a multiple of 2, 3, or 5."
    else
        echo "$1 is not a multiple of 2, 3, or 5."
    fi
}

check_multiples 30
```

### 5. Մեկ հրամանի միջոցով ստեղծել նոր ֆայլ և այդ ֆայլին ավելացնել կատարելու թույլտվություն։

```bash
echo "This is a test file." > new_file.txt && chmod +x new_file.txt
```

### 6. Մեկ հրամանի միջոցով ստուգել, թե արդյոք գոյություն ունի dir անունով դիրեկտորիա, և, եթե գոյություն չունի, ապա ստեղծել։

```bash
[ -d dir ] || mkdir dir
```

### 7. Գրել սկրիպտ, որը կստուգի, թե արդյոք տրված թիվը գտնվում է սահմանված միջակայքում։ Ստուգվող թիվը և միջակայքի սահմանների թվերը ներմուծել read հրամանի միջոցով։ Իրականացնել տվյալների վավերացում։

```bash
#!/bin/bash

read -p "Enter a number: " number

read -p "Enter the lower bound of the range: " lower_bound
read -p "Enter the upper bound of the range: " upper_bound

if [ "$number" -ge "$lower_bound" ] && [ "$number" -le "$upper_bound" ]; then
    echo "The number $number is within the specified range [$lower_bound, $upper_bound]."
else
    echo "The number $number is outside the specified range [$lower_bound, $upper_bound]."
fi

```
OUTPUT:
```bash
Enter a number: 56
Enter the lower bound of the range: 50
Enter the upper bound of the range: 100
The number 56 is within the specified range [50, 100].
```

### 8. Գրել սկրիպտ, որը որպես ներմուծվող արժեք կստանա մեկ բառ, և կստուգի արդյոք այն համընկնում է "Secret" բառի հետ։ read հրամանը կատարել այնպես, որ ներմուծված արժեք պահպանվի REPLY փոփոխականի մեջ, իսկ ներմուծումն իրականացնելիս տառերը չցուցադրվեն էկրանին։

```bash
#!/bin/bash

read -s -p "Enter a word: " REPLY
echo

if [ "$REPLY" = "Secret" ]; then
    echo "You entered the secret word!"
else
    echo "The entered word is not the secret word."
fi

```
OUTPUT:
```bash
# REPLY = SECRETE
The entered word is not the secret word.
```
### 9. Գրել սկրիպտ, որը որպես ներմուծվող արժեք կստանա ֆայլի անուն։ Վավերացնել անունը հետևյալ կանոններով․ կարող է պարունակել տառեր, թվեր, - . _ սիմվոլները։ Եթե նման ֆայլ գոյություն չունի, ապա ստեղծել։ Ցուցադրել համապատասխան հաղորդագրություն ֆայլի ստեղծման կամ առկայության մասին։

```bash
#!/bin/bash

read -p "Enter a file name: " fileName

pattern='^[a-zA-Z0-9_.-]+$'

if [[ $fileName =~ $pattern ]]; then
    echo "The entered file name is valid."
    if [ -e "$fileName" ]; then
        echo "The file \"$fileName\" already exists."
    else
        touch "$fileName"
        echo "The file \"$fileName\" has been created."
    fi
else
    echo "Invalid file name. File names can only contain letters, numbers, hyphen, underscore, and dot."
fi

```

OUTPUT:
```bash
Enter a file name: hello_world
The entered file name is valid.
The file "hello_world" has been created.
```

### 10. Գրել <<Հաշվիչ>> ծրագիր, որը կստանա ճիշտ 3 արժեք հետևյալ հաջորդականությամբ․ թիվ, գործողություն, թիվ։ Օր՝ 2 + 3։ Ստուգել ներմուծված արժեքների քանակը, և 3-ից տարբեր լինելու դեպքում արտածել հաղորդագրություն սխալի մասին։ Իրականացնել արժեքների վավերացում։ Գործողության համար սահմանել հետևյալ ընդունելի արժեքները․ + - * / **։ Արտածել գործողության արդյունքը։

```bash
#!/bin/bash

calculator() {
    case $2 in
        "+") echo $(($1 + $3));;
        "-") echo $(($1 - $3));;
        "*") echo $(($1 * $3));;
        "/") 
            if [ $3 -ne 0 ]; then
                echo $(($1 / $3))
            else
                echo "Error: Division by zero"
            fi;;
        "**") echo $(($1 ** $3));;
        *) echo "Error: Invalid operator";;
    esac
}

read -p "Enter the first number: " num1
read -p "Enter the operator (+, -, *, /, **): " operator
read -p "Enter the second number: " num2

if [[ "$operator" =~ ^[+\-*/**]$ ]]; then
    result=$(calculator $num1 "$operator" $num2)
    echo "Result: $result"
else
    echo "Error: Invalid operator"
fi

```
OUTPUT:
```bash
Enter the first number: 5
Enter the operator (+, -, *, /, **): **
Enter the second number: 3
Result: 125

```


# Լաբորատոր աշխատանք 7

### 1. Գրել ծրագիր, որը կարտածի [0, 20] միջակայքի զույգ թվերը։ Օգտագործել while ցիկլ։
```bash
number=0

while [ $number -le 20 ]; do
    echo $number
    number=$((number + 2))
done
```
OUTPUT:
```bash 
0
2
4
6
8
10
12
14
16
18
20
```
### 2. Կատարել 1-ին առաջադրանքը՝ օգտագործելով until ցիկլ։
```bash 
#!/bin/bash

number=0

until [ $number -gt 20 ]; do
    echo $number
    ((number+=2))
done
```

### 3. Գրել ծրագիր, որը գտնվում է անվերջ ցիկլի մեջ։ Ցիկլի յուրաքանչյուր իտերացիայում արտածել տվյալ ինդեքսի քառակուսին։ Ցիկլը ավարտել այն պահին, երբ արտածվող թիվը կգերազանցի 1000։ Օգտագործել while ցիկլ։

```bash 
#!/bin/bash

index=0

while [ $((index * index)) -le 1000 ]; do
    echo $((index * index))
    ((index++))
done
```
OUTPUT:
```bash 
0
1
4
9
16
25
36
49
64
81
100
121
144
169
196
225
256
289
324
361
400
441
484
529
576
625
676
729
784
841
900
961
```
### 4. Կատարել 1-ին առաջադրանքը՝ օգտագործելով for ցիկլ։

```bash
#!/bin/bash

for ((count = 0; count <= 20; count += 2)); do
	echo $count
done
```

### 5. Գրել ծրագիր, որը որպես մուտքային տվյալ կստանա ամբողջ թիվ և կարտածի դրա կրկնապատիկը։ Ծրագիրը սկսելիս ցուցադրել հետևյալ հաղորդագրությունը․ Enter an integer number, or enter q to quit: Ամբողջ թիվ մուտքագրելուց հետո ցուցադրել դրա կրկնապատիկը, և կրկին ցուցադրել հաղորդագրությունը՝ մինչև q տառի սեղմումը։

```bash 
while true; do
	read -r -p "Enter an integer or 'q' to exit: " input
	if [ "$input" == "q" ]; then
		break
	fi
	echo "Double of $input is $((input * 2))"
done
```
OUTPUT:
```bash
Enter an integer or 'q' to exit: 5
Double of 5 is 10
Enter an integer or 'q' to exit:
```

### 6. Գրել ծրագիր, որը կստեղծի /home/student դիրեկտորիայի տեքստային ֆայլերի անունները պարունակող ֆայլ։ while ցիկլի միջոցով համարակալել այս ֆայլերի անունները և արտածել։

```bash
index=1
while [ $index -le 5 ]; do
	touch ./file_$index.txt
	index=$((index + 1))
done
```
OUTPUT:
```bash
file_1.txt  file_2.txt  file_3.txt  file_4.txt  file_5.txt
```

### 7. Գրել ծրագիր, որը for ցիկլի միջոցով կարտածի [0, 30] միջակայքում գտնվող 3-ի բազմապատիկ թվերը։
```bash
#!/bin/bash

for ((i = 0; i <= 30; i += 3)); do
  echo $i
done
```
OUTPUT:
```bash
0
3
6
9
12
15
18
21
24
27
30
```
### 8. Գրել ծրագիր, որը for ցիկլի միջոցով կարտածի ընթացիկ դիրեկտորիայի բոլոր տեքստային ֆայլերի անունները։

```bash
for file in *; do
	echo "$file"
done
```

### 9. Գրել ծրագիր, որը որպես արգումենտ կստանա ֆայլերի անուններ, և այդ ֆայլերից յուրաքանչյուրի համար կարտածի ֆայլի ամենակարճ բառը և դրա երկարությունը։
```bash
#!/bin/bash

for file in "$@"; do
  if [ -f "$file" ]; then
    echo "File: $file"
    while IFS= read -r word; do
      if [ -n "$word" ]; then
        echo "Shortest word: $word"
        echo "Length: ${#word}"
        break
      fi
    done < "$file"
    echo "-----------------"
  else
    echo "Error: $file is not a valid file."
  fi
done
```
OUTPUT:
```bash 
#This is a sample text file.
#It contains various words and sentences.
File: example.txt
Shortest word: It
Length: 2
-----------------
```
### 10. Գրել ծրագիր, որը որպես արգումենտներ կստանա ֆայլերի անուններ, և դրանցից յուրաքանչյուրի համար կստուգի, թե արդյո՞ք տվյալ ֆայլը գոյություն ունի, թե ոչ։ Գոյություն ունենալու դեպքում ստուգել, թե արդյո՞ք ֆայլն ունի կարդալու թույլտվություն։ Արտածել համապատասխան հաղորդագրություններ։
```bash
#!/bin/bash

for file in "$@"; do
  if [ -e "$file" ]; then
    echo "File '$file' exists."
    if [ -r "$file" ]; then
      echo "File '$file' is readable."
    else
      echo "Error: File '$file' is not readable."
    fi
  else
    echo "Error: File '$file' does not exist."
  fi
  echo "-----------------"
done
```
OUTPUT:
```bash
File 'file1.txt' exists.
File 'file1.txt' is readable.
-----------------
File 'file2.txt' exists.
File 'file2.txt' is readable.
-----------------
Error: File 'non_existent_file.txt' does not exist.
-----------------
```


# Լաբորատոր աշխատանք 8
### 1. Գրել ծրագիր, որը ինտերակտիվ ռեժիմում կստանա [0, 3] միջակայքի որևէ թիվ, ևարգումենտի արժեքից կախված կկատարի հետևյալ գործողությունները․
* 0 – ավարտել ծրագիրը։
* 1 – արտածել /home/student դիրեկտորիայի ֆայլերի ցուցակը։
* 2 – արտածել /home/student դիրեկտորիայի տեքստային ֆայլերի քանակը։
* 3 – արտածել աշխատանքային դիրեկտորիան։
### Գործողությունները կրկնել մինչև 0 արժեքի ներմուծումը։ Օգտագործել case օպերատոր։
```bash
#!/bin/bash

while true; do
    echo "Enter a number (0 to exit):"
    read choice

    case $choice in
        0)
            echo "Exiting the script."
            break
            ;;
        1)
            echo "Listing files in /home/student directory:"
            ls /home/student
            ;;
        2)
            echo "Counting text files in /home/student directory:"
            count=$(find /home/student -type f -name "*.txt" | wc -l)
            echo "Number of text files: $count"
            ;;
        3)
            echo "Displaying the working directory:"
            pwd
            ;;
        *)
            echo "Invalid choice. Please enter a number between 0 and 3."
            ;;
    esac
done

```
OUTPUT:
```bash
Enter a number (0 to exit):
1
Listing files in /home/student directory:
file1.txt
file2.txt
document.txt
...

Enter a number (0 to exit):
2
Counting text files in /home/student directory:
Number of text files: 5

Enter a number (0 to exit):
3
Displaying the working directory:
/home/student

Enter a number (0 to exit):
0
Exiting the script.
```
### 2. Գրել ծրագիր, որը որպես արգումենտ կստանա տարվա ամսի անունը և կվերադարձնի տվյալ ամսում առկա օրերի քանակը։ Օգտագործել case օպերատոր։
```bash
#!/bin/bash

echo "Enter the name of a month:"
read month

case $month in
    "January" | "March" | "May" | "July" | "August" | "October" | "December")
        days=31
        ;;
    "April" | "June" | "September" | "November")
        days=30
        ;;
    "February")
        days=28
        ;;
    *)
        echo "Invalid month name"
        exit 1
        ;;
esac

echo "The number of days in $month is $days."
```
OUTPUT:
```bash
Enter the name of a month:
February
The number of days in February is 28.
```

### 3. Գրել <<Հաշվիչ>> ծրագիր, որը կստանա ճիշտ 3 արժեք հետևյալ հաջորդականությամբ․ թիվ, գործողություն, թիվ։ Օր՝ 2 + 3։ Արժեքները ներմուծել ինտերակտիվ ռեժիմում (read հրամանի միջոցով)։ Գործողության համար սահմանել հետևյալ ընդունելի արժեքները․ + - * / **։ Արտածել գործողության արդյունքը։ Գործողության տիպը որոշելու համար օգտագործել case օպերատոր։

```bash
#!/bin/bash
calculator() {
    case $2 in
        "+") echo $(($1 + $3));;
        "-") echo $(($1 - $3));;
        "*") echo $(($1 * $3));;
        "/") 
            if [ $3 -ne 0 ]; then
                echo $(($1 / $3))
            else
                echo "Error: Division by zero"
            fi;;
        "**") echo $(($1 ** $3));;
        *) echo "Error: Invalid operator";;
    esac
}

read -p "Enter the first number: " num1
read -p "Enter the operator (+, -, *, /, **): " operator
read -p "Enter the second number: " num2

if [[ "$operator" =~ ^[+\-*/**]$ ]]; then
    result=$(calculator $num1 "$operator" $num2)
    echo "Result: $result"
else
    echo "Error: Invalid operator"
fi

```
OUTPUT:
```bash
Enter the first number: 5
Enter the operator (+, -, *, /, **): **
Enter the second number: 3
Result: 125

```
### 4. Գրել ծրագիր, որը որպես հրամանային տողի արգումենտ կստանա ֆայլի անուն։ Եթե ֆայլը գոյություն ունի և ունի կարդալու թույլտվություն, ապա արտածել ֆայլի պարունակությունը, հակառակ դեպքում արտածել համապատասխան հաղորդագրություն։
```bash
#!/bin/bash

# Check if a filename is provided as an argument
if [ $# -eq 0 ]; then
  echo "Usage: $0 <filename>"
  exit 1
fi

filename=$1

if [ -e "$filename" ]; then

  if [ -r "$filename" ]; then
    echo "File content:"
    cat "$filename"
  else
    echo "Error: The file is not readable."
  fi
else
  echo "Error: File not found."
fi
```
OUTPUT:
```bash
#Hello, this is an example file.
#It contains multiple lines.
#This is the third line.

#./readfile.sh example.txt

File content:
Hello, this is an example file.
It contains multiple lines.
This is the third line.
```
### 5. Գրել cp ծրագրի պատճենը՝ առանց cp հրամանից օգտվելու։ Ծրագիրը պետք է որպես արգումենտներ ստանա 2 ֆայլերի անուններ, և պատճենի առաջին ֆայլի պարունակությունը 2-րդի մեջ։ Իրականացնել ծրագրի պատշաճ աշխատանքի համար հարկավոր ստուգումներ (ֆայլը գոյություն ունի, ունի կարդալու թույլտվություն)։
```bash
echo "Enter the first filename: "
read -r file1

echo "Enter the second filename: "
read -r file2

if [ -r "$file1" ]; then
	cat "$file1" >"$file2"
	echo "Content of the file successfully copied."
else
	echo "File $file1 does not exist or is not readable."
fi
```
OUTPUT:
```bash 
#Let's assume you run the script and provide valid filenames as input:
Enter the first filename:
example1.txt
Enter the second filename:
example2.txt
#If they exist and are readable we will see 
Content of the file successfully copied.
```
### 6. Գրել ծրագիր, որը որպես հրամանային տողի արգումենտներ կստանա 2 թիվ և կարտածի այդ թվերի գումարը։ Իրականացնել արժեքների վավերացում։
```bash
if [ "$#" -ne 2 ]; then
	echo "Usage: $0 <num1> <num2>"
	exit 1
fi

num1="$1"
num2="$2"

if ! [[ "$num1" =~ ^[0-9]+$ ]] || ! [[ "$num2" =~ ^[0-9]+$ ]]; then
	echo "Invalid input. Please enter valid numbers."
	exit 1
fi

sum=$((num1 + num2))
echo "The sum of $number1 and $number2 is: $sum"
```
```bash 
./sum.sh 5 7
```
OUTPUT:
```bash 
The sum of 5 and 7 is: 12
```
### 7. Գրել ծրագիր, որը որպես հրամանային տողի արգումենտներ կստանա կամայական քանակով արժեքներ և նույնությամբ կարտածի այդ արժեքները։ Օգտագործել while ցիկլ և shift օպերատոր։
```bash
#!/bin/bash

if [ "$#" -eq 0 ]; then
    echo "No arguments provided."
    exit 1
fi

while [ "$#" -gt 0 ]; do
    echo "$1"
    shift
done
```
```bash
./print_args.sh arg1 arg2 arg3
```
OUTPUT:
```bash
arg1
arg2
arg3

```
### 8. Իրականացնել 7-րդ կետը՝ օգտագործելով for ցիկլ և $@ հատուկ փոփոխականը։
```bash
for arg in "$@"; do
	echo "Argument: $arg"
done
```
### 9. Գրել ծրագիր, որը որպես հրամանային տողի արգումենտներ կստանա կամայական քանակով թվեր և կարտածի այդ թվերի գումարը։
```bash
sum=0

for arg in "$@"; do
	if [[ "$arg" =~ ^[0-9]+$ ]]; then
		sum=$((sum + arg))
	else
		echo "Invalid input. Please enter valid numbers."
		exit 1
	fi
done

echo "Sum: $sum"
```
```bash
./sum.sh 5 10 15
```
OUTPUT:
```bash
Sum: 30
```
### 10. Գրել ծրագիր, որը որպես հրամանային տողի արգումենտներ կստանա կամայական քանակով թվեր և կարտածի զույգ թվերի քանակը։
```bash
#!/bin/bash

if [ "$#" -eq 0 ]; then
    echo "Usage: $0 <num1> [num2 ...]"
    exit 1
fi

even_count=0

while [ "$#" -gt 0 ]; do
    num="$1"
    
    if ! [[ "$num" =~ ^[0-9]+$ ]]; then
        echo "Invalid input: $num is not a valid integer."
        exit 1
    fi
    
    if [ $((num % 2)) -eq 0 ]; then
        even_count=$((even_count + 1))
    fi

    shift
done

echo "Count of even numbers: $even_count"
```
```bash
./even_count.sh 5 10 15 20
```
OUTPUT:
```bash
Count of even numbers: 2
```