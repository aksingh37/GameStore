class Game:
	
	    def __init__(self, name, company, storage, price = 0 ):
	        self.name = name
	        self.company = company
	        self.storage = storage
	        self.price = price
	
	class GameStore:
	
	    games = []
	    selectedGame = []
	
	    def __init__(self, name, company, storage, price ):
	        g = Game(name,company,storage = storage, price = price)
	        self.games.append(g)
	    
	    def show(self):
	        print("############### AVAILBALE GAMES ###############")
	        
	        pos=1
	
	        for game in self.games:
	            print("###############", pos, "###############") 
	            pos += 1   
	            self.display(game)
	            
	    
	    def select(self):
	        print("############### SELECT A GAME ###############")
	        print("############### HOW MANY GAME YOU WANT? ###############")
	        neededGames = int(input())
	
	        for i in range(0, neededGames ):
	            Print("############### INPUT THE GAME NO ###############")
	            selectedGame = int(input())
	            Print("############### SELECTED A GAME ###############")
	            b = self.getGameById(selectedGame - 1)
	            self.selectedGame.append(b)
	            print(self.display(g))
	
	    def getGameById(self, position):
	        return self.games[position]
	
	    def display(self, game):
	        print("Game name : ", game.name)
	        print("Game STORAGE : ", game.storage)
	        print("Game Price : ", game.price)
	        print("Game Company : ",game.company)
	
	    def selectedGames(self):
	        return self.selectedGame
	
	
	class BillCounter:
	
	    games = []
	    def __init__(self, myGames):
	        self.games = myGames
	    
	    def display(self):
	        pos = 1
	        for game in self.games:
	            print("############### BILL COUNTER GAMES ###############")
	            pos += 1
	            print("############### GAME NO", pos," ###############")
	            print("Game name : ", game.name)
	            print("Game STORAGE : ", game.storage)
	            print("Game Price : ", game.price)
	            print("Game Company : ",game.company)
	
	    def getTotal(self):
	        total = sum(map(lambda g : g.price, self.games))
	        print("############### TOTAL PRICE ###############”)
	        print(total)
	    
	    def getMax(self):
	        total = max(map(lambda g : g.price, self.games))
	        print("############### MAX PRICE ###############")")
	        print(total)
	
	    def getMin(self):
	        total = min(map(lambda g : g.price, self.games))
	        print("############### MIN PRICE ###############")
	        print(total)
	
	    def getCompanys(self):
	        print("############### COMPANYS ###############")
	        companys = map(lambda a : a.company, self.games)
	        for company in companys:
	            print(company)
	    
	
	    def delete(self):
	        print("############### IF YOU WANT TO DELETE PRESS 1 ELSE 0 ###############")
	        choice = int(input())
	        if (choice == 1):
	            print("############### ENTER GAME NUMBER ###############")
	            position = int(input())
	            self.games.remove(self.getGameById(position))
	        else:
	            print("############### NO GAMES ###############")
	
	    def getGameById(self, position):
	        return self.games[position - 1]
	
	    
	if "__MAIN__":
	
	    print("############### WELCOME TO GAME STORE ###############")
	
	    gs = GameStore("PACMAN", "NINTENDO", "156MB", 150)
	    gs = GameStore("PUBG", "KRAFTON", "17GB", 800)
	    gs = GameStore("CALL OF DUTY", "ACTIVISION", "45GB", 999)
	    gs = GameStore("LAST OF US", "EA", "52GB", 699)
	    
	    gs.show()
	
	    gs.select()
	
	    selectedGames = gs.selectedGames()
	    
	    print(selectedGames)
	
	    bc = BillCounter(selectedGames)
	
	    bc.display()
	
	    bc.delete()
	
	    bc.getTotal()
	
	    bc.getMax()
	
	    bc.getMin()
	
	    bc.getCompanys()
