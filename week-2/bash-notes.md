 $ cat <file> #koristimo za ispis sadrzaja fajla

$ pwd #prikazi u kom sam direktorijumu

$ ls -la #izlistaj sve fajlove, -la ce izlistati i skrivene

$ cat readme #prikazi readme file

$ cd .. #idi jedan korak unazad (Back)

$ cd bandit1 #udji u folder bandit1

$ cat < - #procitaj - fajl

$ cat spaces\ in\ this\ filename #procitaj fajl pod nazivom spaces in this filename

$ cd inhere 

$ cat .hidden #procitaj skriveni .hidden fajl

$ ls -la -lh #izlijstaj sve fajlove, i one skrivene, i prikazi njihovu velicinu

$ find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null

$ grep "millionth" data.txt #pronadji rijec "millionth" u fajlu data.txt

$ cat data.txt | sort | uniq -u #procitaj data.txt fajl, prikazi jedinstvene vrijednosti koje se pojavljuju samo jednom

$ strings data.txt #izvuci i prikazi stringove