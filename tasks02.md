#tasks02 safari

q1. The names of the animals in the Bird house.
```sql
SELECT animals.name FROM animals JOIN enclosures ON enclosures.id = animals.enclosures_id WHERE enclosures.id = 2
```

q2. The names of the staff working in the big cat field.
```sql
SELECT DISTINCT(staff.name) FROM staff INNER JOIN assignments ON staff.id = assignments.employeeId INNER JOIN enclosures ON assignments.enclosureId = enclosures.id WHERE enclosureId = 1
```

q3. The staff wokring on the closed enclosures. 
```sql
SELECT DISTINCT (staff.name) FROM staff INNER JOIN assignments ON staff.id = assignments.employeeId INNER JOIN enclosures ON assignments.enclosureId = enclosures.id WHERE closedformaintenance = '1'
```

q4. The name of the enclosure with the oldest animal.
```sql
SELECT enclosures.name FROM animals INNER JOIN enclosures ON animals.enclosures_id = enclosures.id ORDER BY animals.age DESC, animals.name limit 1
```
q5. the total number of animal types that a given keeper has been assigned to.
```sql
SELECT COUNT (DISTINCT(animals.type)) FROM assignments INNER JOIN enclosures ON enclosures.id = assignments.enclosureId INNER JOIN animals ON animals.enclosures_id = enclosures.id WHERE employeeid = 6 
```
q6. The number of different keepers who have been assigned to work in a given enclosure.
```sql
SELECT COUNT (DISTINCT (assignments.employeeid)) FROM enclosures JOIN assignments ON enclosures.id = assignments.enclosureid WHERE enclosureid = 3
```
q7.The names of the other animals sharing an enclosure with a given animal.
```sql
SELECT name FROM animals  WHERE animals.enclosures_id = 3 and animals.id != 12
```
