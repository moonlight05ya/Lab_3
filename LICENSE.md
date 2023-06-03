from datetime import datetime


class Worker:
    def __init__(self, codename, age, dob, gender, height_cm, weight_kg, languages):
        self.codename = codename
        self.age = age
        self.dob = datetime.strptime(dob, '%Y-%m-%d')
        self.gender = gender
        self.height_cm = height_cm
        self.weight_kg = weight_kg
        self.languages = languages

    def __str__(self):
        return f" {self.codename} ({self.age} років, то народився {self.dob.date()}, {self.gender})"
         def compare_age(self, other):
        if self.age > other.age:
            return f"{self.codename} старше ніж {other.codename}"
        elif self.age < other.age:
            return f"{self.codename} молодший за {other.codename}"
        else:
            return f"{self.codename} і {other.codename} одного віку"

    def compare_dob(self, other):
        if self.dob < other.dob:
            return f"{self.codename} народився раніше {other.codename}"
        elif self.dob > other.dob:
            return f"{self.codename} народився після {other.codename}"
        else:
            return f"{self.codename} і {other.codename} народилися в один день"

    def compare_gender(self, other):
        if self.gender == other.gender:
            return f"{self.codename} і {other.codename} мають одну стать ({self.gender})"
        else:
            return f"{self.codename} і {other.codename} мають різну стать ({self.gender} і {other.gender})"

    def compare_height(self, other):
        if self.height_cm > other.height_cm:
            return f"{self.codename} вищий за {other.codename}"
        elif self.height_cm < other.height_cm:
            return f"{self.codename} нижче за {other.codename}"
        else:
            return f"{self.codename} і {other.codename} одного зросту"

    def compare_weight(self, other):
        if self.weight_kg > other.weight_kg:
            return f"{self.codename} важить більше ніж {other.codename}"
        elif self.weight_kg < other.weight_kg:
            return f"{self.codename} важить менше ніжn {other.codename}"
        else:
            return f"{self.codename} і {other.codename} важать однаково"

    def compare_languages(self, other):
        common_languages = set(self.languages) & set(other.languages)
        if common_languages:
            return f"{self.codename} і {other.codename} знають {len(common_languages)} спільну(і) мову(и): {', '.join(common_languages)}"
        else:
            return f"{self.codename} і {other.codename} не знають спільних мов"


worker1 = Worker("Марк", 36, "1987-04-28", "Чоловік", 183, 70, ["Англійська", "Французька", "Китайська"])
worker2 = Worker("Соломія", 28, "1995-09-14", "Жінка", 170, 64, ["Англійська", "Корейська", "Португальська"])

print(worker1.compare_age(worker2))
print(worker1.compare_dob(worker2))
print(worker1.compare_gender(worker2))
print(worker1.compare_height(worker2))
print(worker1.compare_weight(worker2))
print(worker1.compare_languages(worker2))
