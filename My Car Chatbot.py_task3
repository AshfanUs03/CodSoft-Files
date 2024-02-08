import random

class SimpleChatbot:
    def __init__(self):
        self.responses = {
            'greetings': ['hello', 'hi', 'hey', 'greetings'],
            'about_car': ['availability of car', 'what variant is this car', 'new features',
                          'what\'s the on-road price', 'color options'],
            'support': ['book a test ride', 'appointment for delivery', 'time and date'],
            'farewell': ['goodbye', 'see you later', 'bye', 'thanks for your help', 'exit']
        }

    def get_intent(self, user_input):
        for intent, patterns in self.responses.items():
            for pattern in patterns:
                if pattern in user_input:
                    return intent
        return 'general_query'

    def respond(self, intent):
        if intent == 'greetings':
            return "Hello! What can I help you with?"
        elif intent == 'about_car':
            return ("Yes, the car you're looking for is available.",
                    "The variant of the car is Harrier Smart.",
                    "It packs with a 12.2-inch touchscreen infotainment system, lane change alert, blind spot detection.",
                    "It's priced at ₹15,49,000.",
                    "The color options available are 'Sunlit Yellow', 'Coral Red', 'Pebble Grey', 'Oberon Black', 'Lunar White', 'Seaweed Green'")
        elif intent == 'support':
            return random.choice(["When can I book a test ride for you?" or "May I know your free date and time?"])
        elif intent == 'farewell':
            return random.choice(["Goodbye!", "Glad to help you!", "Goodbye! If you have any more queries, feel free to ask."])
        else:
            return "Sorry, I couldn't get you. Can you please provide more information?"

    def chat(self):
        print("Welcome to the ChatCar! Type 'exit' to end the conversation.")

        while True:
            user_input = input("You: ").lower()

            if user_input == 'exit':
                print(f"ChatCar: {self.respond('farewell')}")
                break

            intent = self.get_intent(user_input)
            response = self.respond(intent)
            print("ChatCar:", response)

if __name__ == "__main__":
    chatbot = SimpleChatbot()
    chatbot.chat()
    


