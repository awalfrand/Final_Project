import datetime
import requests
import json
import os
from IPython import embed

#api information

BetterDoctor_api_key = os.environ.get("BetterDoctor_API_KEY") or "Oops! Please enter a valid key."
BetterDoctor_api_url = 'https://api.betterdoctor.com/2016-03-01/doctors?location=37.773,-122.413,100&skip=2&limit=10&api_key=' + BetterDoctor_api_key;

openFDA_label_api_key = os.environ.get("openFDA_label_API_KEY") or "Oops! Please enter a valid key."
openFDA_label_url = 'https://api.fda.gov/drug/label.json'

openFDA_event_api_key = os.environ.get("openFDA_event_API_KEY") or "Oops! Please enter a valid key."
openFDA_event_url = 'https://api.fda.gov/drug/event.json'

#instructions for looping through data in each API

openFDA_label_request_url = "https://api.fda.gov/drug/label.json"
response_label = requests.get(openFDA_label_request_url)
def parse_response_label(response_text_label):

    if isinstance(response_text_label, str):
        response_text_label = json.loads(response_text_label)

openFDA_event_request_url = "https://api.fda.gov/drug/event.json"
response_event = requests.get(openFDA_event_request_url)
def parse_response_event(response_text_event):

    if isinstance(response_text_event, str):
        response_text_event = json.loads(response_text_event)

BetterDoctor_request_url = "'https://api.betterdoctor.com/2016-03-01/doctors?location=37.773,-122.413,100&skip=2&limit=10&user_key=' + BetterDoctor_api_key;"
response_BetterDoctor = requests.get(BetterDoctor_request_url)
def parse_response_BetterDoctor(response_text_BetterDoctor):

    if isinstance(response_text_BetterDoctor, str):
        response_text_BetterDoctor = json.loads(response_text_BetterDoctor)

#interface

def menu(username="@Aria"):
    menu = """
    -----------------------------------
            HELP YOUR HEALTH!
    -----------------------------------
    Welcome {username}!
    Here's all the things you can do with Help Your Health! Please choose from the menu options below.
        options   | description
        --------- | ------------------
        'Info'    | Display all information about a drug.
        'Compare' | Compare two or more drugs among a set of characteristics.
        'Doctor'  | Find a doctor in your area to get more information.

    What would you like to do today?: """
    return menu

#user input

def run():
    # Read attributes from file...
    products_label = read_products_from_file(response_text_label)
    operation = operation.title()
    input(operation)

    results_label = []
    drug_label = response_text["results"]
    for results_label in drug_label:
        results_label = {
            "brand_name": results_label["1.Brand Name"],
            "generic_name": results_label["2. Generic Name"],
            "purpose": results_label["3. Purpose"],
            "stop_use": results_label["4. Stop Use If"]
        }
        results.append(result_label)
    return results_label

    products_event = read_products_from_file(response_text_event)
    operation = operation.title()
    input(operation)

    results_event = []
    drug_event = response_text["results"]
    for results_event in drug_event:
        results_event = {
            "manufacturer_name": results_event["1.Manufacturer Name"],
        }
        results.append(result_event)
    return results_event

    products_BetterDoctor = read_products_from_file(response_text_BetterDoctor)
    operation = operation.title()
    input(operation)

    results_BetterDoctor = []
    drug_BetterDoctor = response_text["Results"]
    for results_BetterDoctor in drug_BetterDoctor:
        results_BetterDoctor = {
            "brand_name": results_BetterDoctor["1.Brand Name"],
            "generic_name": results_BetterDoctor["2. Generic Name"],
            "purpose": results_BetterDoctor["3. Purpose"],
            "stop_use": results_BetterDoctor["4. Stop Use If"]
        }
        results.append(result_BetterDoctor)
    return results_BetterDoctor

    if operation == "Info":
        print("Get More Information")
        brand_names_info = input("Please enter the generic or brand name of the drug you would like to learn more about: ")
        matching_products_info = [p for p in results_label if int(p["brand_name"]) == int(results_label)]
        matching_product_info = matching_products_info["brand_name", "generic_name","purpose","stop_use"]
        print("-------")
        print(brand_names_info)
        print(matching_product_info)
        print("-------")

    elif operation == "Compare":
        print("Compare")
        while True:
            brand_names = input("Please enter the generic or brand names of the drug you would like to learn more about: ")
            if brand_names == "DONE":
                break
            else:
                brand_name.append(int(brand_names))
        matching_compare = [p for p in results_label if int(p["brand_name"]) == int(results_label)]
        matching_product_compare = matching_compare["brand_name", "generic_name","purpose","stop_use"]
        print("-------")
        print(brand_names)
        print (matching_product_compare)
        print("-------")

    elif operation == "Doctor":
        print("Let's find you a doctor")
        Find_a_Doctor=input("Please enter your postal code: ")
        matching_doctor = [p for p in results_BetterDoctor if int(p["zip"]) == int(results_BetterDoctor)]
        matching_product_doctor = matching_doctor["first_name", "middle_name", "last_name", "name", "visit_address", "website","accepts_new_patients","insurancce_uids"]
        print("Here's a list of doctors in your area: ")
        print("-------")
        print(Find_a_Doctor)
        print (matching_product_doctor)
        print("-------")

    else:
        print("Please select a valid option")
