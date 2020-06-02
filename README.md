# AWS

Discover instance ID using `wget` or `curl`:

```
wget -q -O - http://169.254.169.254/latest/meta-data/instance-id
curl http://169.254.169.254/latest/meta-data/instance-id
```


# Excel

## Get the number of occurrences of a text on a given string

Considering cell `G4` is the target:

```=(LEN(G4)-LEN(SUBSTITUTE(G4;"search";"")))/LEN("search")```

# MySQL

Generating an UUID4 using query:

```sql
SELECT LOWER(CONCAT(
    LPAD(HEX(FLOOR(RAND() * 0xffff)), 4, '0'),
    LPAD(HEX(FLOOR(RAND() * 0xffff)), 4, '0'), '-',
    LPAD(HEX(FLOOR(RAND() * 0xffff)), 4, '0'), '-',
    '4',
    LPAD(HEX(FLOOR(RAND() * 0x0fff)), 3, '0'), '-',
    HEX(FLOOR(RAND() * 4 + 8)),
    LPAD(HEX(FLOOR(RAND() * 0x0fff)), 3, '0'), '-',
    LPAD(HEX(FLOOR(RAND() * 0xffff)), 4, '0'),
    LPAD(HEX(FLOOR(RAND() * 0xffff)), 4, '0'),
    LPAD(HEX(FLOOR(RAND() * 0xffff)), 4, '0')))
```

# PostgreSQL

## User administration

```sql
\c postgres;
CREATE USER "full.name" WITH PASSWORD 'letmein';
ALTER ROLE "full.name" WITH LOGIN;
GRANT bi_users TO "full.name";
GRANT "outro.user" TO "full.name";
```


# Kubernetes

## Secrets

Update a secret

```bash
kubectl create secret generic production-tls \
    --from-file=./tls.key --from-file=./tls.crt --dry-run -o yaml | \
    kubectl apply -f -
```


# Python

## Files

Check if a file exists:

```python
import os.path
os.path.isfile(fname)
```

## Arrays

```python
arr = [1,2,3]

# Add elements
arr.append(4)
arr.append(4)

# Get the number of unique elements
uniques = set(arr)
```

## Objects

Python copies object by reference. Use `copy()` if you need a local copy:

```python
oldDict = {"a": False}
newDict = oldDict.copy()
newdict["a"] = True
```

## Dictionaries

Get and remove an element from the dictionary:

```python
d = {'a': 10, 'b': 20, 'c': 30}
d.pop('b') #20
d # {'a': 10, 'c': 30}
```

## Strings

Substrings:

```python
string = "Hello"
string[:2] # 'He'
string[2:] # 'llo'
string[-1:] # 'o'
```

## PIP

Create a `requirements.txt` file:

```bash
pip freeze > requirements.txt
```
