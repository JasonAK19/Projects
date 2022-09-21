def run_metro_system(metroSystemName):
    """
           Metro system name
           :return: no return
           Description: while loop that runs program and checks inputs
           """
    x = input(f"[{metroSystemName}] >>> ")
    while x != "quit":

        commands = x.strip().split()

        if commands[0:2] == ["create", "station"]: # checks the indexes of the input to determine which function to call
            if len(commands) < 3 or len(commands) > 3:
                print("create one station at a time")
                x = input(f"[{metroSystemName}] >>> ")
            else:
                create_station(commands[-1], stations)


        if commands[0:2] == ["connect", "stations"]:
            if len(commands) < 5 or len(commands) > 5:
                x = input(f"[{metroSystemName}] >>> ")
            else:
                connect_stations(commands[2], commands[3], commands[4], stations)


        if commands[0:2] == ["display", "stations"]:
            display_stations(stations)

        if commands[0:2] == ["display", "trains"]:
            display_trains(trains)

        if commands[0:2] == ["plan", "trip"]:
            if len(commands) < 4 or len(commands) > 4:
                x = input(f"[{metroSystemName}] >>> ")
            else:
                for x in stations:
                    stations[x]['visited'] = False
                plan_trip(commands[2], commands[3], stations)

        if commands[0:2] == ["create", "train"]:
            if len(commands) < 5 or len(commands) > 5:
                x = input(f"[{metroSystemName}] >>> ")
            else:
                create_train(commands[2], commands[3], commands[4], trains)
                print(trains)

        if commands[0:3] == ["get", "station", "info"]:
            get_station_info(commands[3], stations)

        if commands[0:3] == ["get", "train", "info"]:
            get_train_info(commands[3], trains)

        x = input(f"[{metroSystemName}] >>> ")


def create_station(station_name, stations):
    """
           station_name station dictionary
           :return: station dictionary
           Description: creates a key in the stations dictionary that contains another dictionary as it's value
           """
    if station_name not in stations: # checks for duplicate statioms
        stations[station_name] = {"connected": [], "lines": [], "visited": False} # creates stations and has makes nested dictionairy
    else:
        print("station already exist")

    return stations


def connect_stations(first_station, second_station, line_name, stations):
    """
           first station second station line name station dictionary
           :return: station dictionary
           Description: makes a connect between stations by adding the names in multiple list
           """
    if first_station in stations and second_station in stations:
        stations[first_station]["connected"].append(second_station) # adds the connected station names to each connected list
        stations[second_station]["connected"].append(first_station)
        if line_name not in stations[first_station]["lines"]: # checks to find duplicate line names and then add the line names to the line list
            stations[first_station]["lines"].append(line_name)
        if line_name not in stations[second_station]["lines"]:
            stations[second_station]["lines"].append(line_name)

    return stations


def plan_trip(starting_station, ending_station, stations):
    """
           starting_station ending station, stations dictionary
           :return: empty list
           Description: loops through dictionary until it finds the desired station
           """
    location = []

    if starting_station not in stations or ending_station not in stations:
        print(f"{starting_station} or {ending_station} do not exist")
        repeat = input(">>>")
    if starting_station == ending_station:
        print(stations[starting_station]["lines"][0], "---->", ending_station)
        return ending_station
    else:
        location.append(starting_station)
        print(location[0], "--->", stations[starting_station]["lines"][0], "---->", ending_station)
        stations[starting_station]['visited'] = True

        for new_place in stations[starting_station]['connected']:
            if not stations[new_place]['visited']:
                trip_plan = plan_trip(new_place, ending_station, stations)
                if trip_plan:
                    return starting_station + trip_plan

        return []


def create_train(train_id, line_name, starting_position, trains):
    """
           Train_id, line_name, starting_position, train dictionary
           :return: no return
           Description: makes a train out of the information in the station dictionary
           """
    if starting_position not in stations and line_name not in stations[starting_position]["lines"]: # checks for existing stations and lines
        print("station does not exists")
    else:
        trains[train_id] = {"lines": [line_name], "starting position": [starting_position]}


def display_stations(stations):
    """
           station dictionary
           :return: no return
           Description: displays all station names
           """
    for key in stations.keys(): #loops through the station dictionary and prints names
        print(key)


def display_trains(trains):
    """
           train dictionary
           :return: no return
           Description: displays information for all trains
           """
    for key in trains.keys():
        print(f"*** Information for train {key} ***")
        print("lines :", " ".join(trains[key]["lines"]))
        print("current position :", " ".join(trains[key]["starting position"]))


def get_station_info(station_name, stations):
    """
           :parameter: station name
           :return: no return
           Description: displays information for a certain station
           """

    print(f"*** Information for station {station_name} ***")
    print("connected to:", " ".join(stations[station_name]["connected"]))
    print("line names:", " ".join(stations[station_name]["lines"]))


def get_train_info(train_id, trains):
    """
    parameter: train_id, train dictionary
    no return
    description : displays information in the train dictionary



    """
    print(f"*** Information for train {train_id} ***")
    print("current position:", " ".join(trains[train_id]["starting position"]))
    print("line :", " ".join(trains[train_id]["lines"]))


if __name__ == '__main__':
    stations = dict()
    trains = dict()

    metroSystem = input(">>>> ")
    run_metro_system(metroSystem)
