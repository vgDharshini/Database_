import sqlite3
# Connect to SQLite database (or create it if it doesn't exist)
connect= sqlite3.connect('contact_book.db')
cursor= connect.cursor()

# Create table
cursor.execute('''
    CREATE TABLE contacts
    (ID INTEGER PRIMARY KEY,
    Name TEXT,
    Cell TEXT,
    Email TEXT)
''')
# Insert 5 rows of data
data= [
    (1, 'dharshini', '4567812345', 'DHACHU@example.com'),
    (2, 'deeksha', '0987345621', 'DEE@example.com'),
    (3, 'gayana', '1112224488', 'gaya@example.com'),
    (4, 'zoya', '9876556666', 'ZO@example.com'),
    (5, 'sherya', '7778889999', 'SHER@example.com'),
]
cursor.executemany('INSERT INTO contacts VALUES (?,?,?,?)', data)
# Commit the changes
connect.commit()

cursor.execute('SELECT * FROM contacts')

rows = cursor.fetchall()

print("ID\tName\t\tCell#\t\t\tEmail")
print("-" * 50)
for row in rows:
    print(f"{row[0]}\t{row[1]}\t\t{row[2]}\t\t{row[3]}")

connect.close()
