# Hashing, Salting, Key Stretching Study Notes

## Hashing
A one way process that turns a password into a scrambled fixed size value.  
The same input always produces the same output if hashed once.

## Salting
A random value added to each password before hashing so identical passwords do not produce matching hashes.  
Salts break rainbow tables and prevent attackers identifying reused passwords.

## Key Stretching
Repeating hashing many times so computing the final value takes noticeable time.  
The stored hash is only correct after thousands of rounds so attackers must repeat the same slow steps.

## Why Attacks Slow Down
Attackers rely on fast guessing.  
Stretching forces every guess to walk through thousands of hash cycles which removes their speed advantage.

## Flow Diagram
password
↓
salt added
↓
many rounds of hashing (bcrypt or PBKDF2)
↓
final hash stored in database

## Misuse Case
No salt or stretching means attackers can crack millions of passwords quickly or match users with the same password.

## Exam Mapping
- bcrypt, scrypt, PBKDF2 = key stretching  
- Rainbow table resistance = salting  
- One way protection = hashing