# Actividad_Integradora_Multiagentes

## Introduccion

En base al juego de la vida por John Conway se modificaron las reglas existentes para simular la infeccion de la enfermedad causada por el virus de SARS-COV2, Covid-19. En base a este se genero un codigo usando mesa para representar la infeccion de manera grafica.
## Agentes Involucrados
Dentro de este codigo se usa el agente que se proporcion dentro del juego de la vida de conway GameLifeModel el cual representaba una celula muerta o viva la cuales cambiaban de estado en base a la reglas originales. Se altero el agente inicial GameLifeAgent para representar las reglas de la represenacion de la enfermedad COVID-19.
Se altero el agente para que tuviera 3 estados diferentes

- Verde = Personas Vivas No Infectadas
- Azul = Personas Vivas Infectadas
- Rojo = Personas Difuntas

Cuando un agente es marcado verde este analiza sus celdas vecinas haciendo asi que el entorno analizado solo sea las celdas vecinas a las celdas verdes y en base a eso  mandar a llamar una funcion la cual cuenta cuantas celdas vecinas estan infectadas y se se tiene 4 celdas vecinas ifectadas esta se infecta una vez infectada se convierta en una celda azul.

Cuando un agente es marcado azul este tiene una probalidad del 10% de convertirse en una celda roja.

Cuando un agente es marcado rojo este deja de tener acciones.

Las variables que determinan el funcionamiento del sistemas son las siguientes
- infected_neighbours 
- live_neighbours
Estas 2 variables se usan dentro del agente principal GameLifeModel y se usan para representar la cantidad de vecinos infectados que una celda verde(No infectada) tiene en base a esto se lleva a cabo las condiciones que revisan si una celda verde tiene 4 o mas vecinos infectados y en base a eso cambiar el estado a rojo en base al resultado de probabiliidad.

Para llevar acabo la sumulacion se usa la funcion get_grid(self) la cual permite guardar el grid para cada uno de los agentes y su estado, se guarda el estado de las celdas para cada uno de los steps.
En base a la animacion que como mencionado anteriormente se hace usando un matriz con los estados de todos los agentes, se usaron 3 funciones mas para analizar los resultados de la representacion de la infeccion en base a las reglas establecidad.
-get_life()
-get_death()
-get_infected()
Estas 3 funciones estan encargadas de analizar y contar la cantidad de celdas verdes, rojas y azules en cada uno de los steps graficados para asi llevar a cabo diferentes graficas con las cuales se representaria la infeccion del COVID-19.

## Variables importantes dentro del model

    *def __init__(self, width, height):
        self.width = width
        self.height = height

        self.reset()

    def reset(self):
        self.num_agents = self.width * self.height
        self.grid = SingleGrid(self.width, self.height, True)
        self.schedule = SimultaneousActivation(self)*
        
Dentro del model se tienen las funciones aneteriores, las cuales tienen las siguientes variables
- width
- height
- self.num_agents 
- self.grid

Estas variables representan el tamaño de la matriz al igual que el numero de agentes dentro de la celda, teniendo asi un agente por celda dentro del grid.
        
En base a este modelo de simualcion de COVID-19 se representa en la mayoria de los casos que la mayoria de las celdas se infecta teniendo solo un porcentaje minimo de celdas no infectadas al final de la simualcion y teniendo un porcentaje de celdas rojas o humanos muertos un poco menor al 10%.
