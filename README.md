# Bash Scripting ( Part 3 )
---
## Exercice 1

* **q1**

![image](https://user-images.githubusercontent.com/91763346/206732438-a2c8b60d-b061-4fd8-a3ee-34dbe913b6dd.png)

![image](https://user-images.githubusercontent.com/91763346/206724414-f4737399-fcad-4e25-8631-b2fc25f1715d.png)

* **q2**

![image](https://user-images.githubusercontent.com/91763346/206725402-7a5246e8-3e7f-4769-bb58-773493f4a610.png)

* **q3**

![image](https://user-images.githubusercontent.com/91763346/206728455-049eaa5a-8d36-44b9-93ca-9799d3e42c70.png)

## Exercice 2

* **q1**

![image](https://user-images.githubusercontent.com/91763346/206729052-9d9a2e6f-dc46-49b4-ad52-07db0d95a06f.png)


* **q2 & q3 & q4**

``` for i in $@; do
  if [[ $i == "-l" ]]; then
    listf=1
  fi
done

#testing for -r
for i in $@; do
  if [[ $i == "-r" ]]; then
    rem=1
  fi
done

#case where -l exists

if [ listf -eq 1 ]; then
  for i in $@; do
    ls ~/Poubelle
  done
fi

#case where -r exists
if [ listf -eq 1 ]; then
  for i in $@; do
    rm ~/Poubelle *
  done
fi

#case where -r and -l exist
if [ listf -eq 1 && rem -eq 1 ]; then
  for i in $@; do
    echo "moving file"
    mv $i ~/Poubelle
    echo "Le dossier poubelle contient"
    ls ~/Poubelle
    echo "Removing files"
    rm ~/Poubelle
  done
else
  for i in $@; do
     echo "moving file"
     mv $i ~/Poubelle
  done
fi

```
