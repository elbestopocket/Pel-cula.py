# Pel-cula.py
Parcial de programación 2do corte 
class Película:
    def __init__(self, código=0, título="", duración=0, director="", prestada=False):
        self.__código = código
        self.__título = título
        self.__duración = duración
        self.__director = director
        self.__prestada = prestada

    def get_código(self):
        return self.__código

    def get_título(self):
        return self.__título

    def get_duración(self):
        return self.__duración

    def get_director(self):
        return self.__director

    def get_prestada(self):
        return self.__prestada

    def set_código(self, código):
        self.__código = código

    def set_título(self, título):
        self.__título = título

    def set_duración(self, duración):
        self.__duración = duración

    def set_director(self, director):
        self.__director = director

    def set_prestada(self, prestada):
        self.__prestada = prestada

    def prestar(self):
        if not self.__prestada:
            self.__prestada = True
            return "La película ha sido prestada."
        else:
            return "La película ya estaba prestada."

    def devolver(self):
        if self.__prestada:
            self.__prestada = False
            return "La película ha sido devuelta."
        else:
            return "La película no estaba prestada."

    def costo_reproducción(self, tarifa_x_minuto):
        coste_total = self.__duración * tarifa_x_minuto
        return f"El costo de reproducir esta película es de: ${coste_total:.2f}"

    def __str__(self):
        estado = "está prestada" if self.__prestada else "no está prestada"
        return (f"La película {self.__código}, titulada «{self.__título}», dirigida por {self.__director}, "
                f"dura {self.__duración} minutos y {estado}")

