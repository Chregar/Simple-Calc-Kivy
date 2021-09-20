from kivy.app import App
from kivy.uix.widget import Widget
from kivy.lang import Builder
from kivy.core.window import Window

Window.size = (300,450)
Builder.load_file('demo.kv')

class MyLayout(Widget):

    '''Clear button'''
    def clear(self):
        self.ids.calc_input.text = "0"

    '''Press button, numbers'''
    def press_button(self,button):
        #Create a variable that contains what was already in the Input box
        prior = self.ids.calc_input.text

        #Test for error
        if "Error" in prior:
            prior = ""

        #Determine if 0 is sitting there
        if prior == "0":
            self.ids.calc_input.text = ""
            self.ids.calc_input.text = f"{button}"
        else:
            self.ids.calc_input.text = f"{prior}{button}"

    def remove(self):
        #Function to remove last char in textbox
        prior = self.ids.calc_input.text
        #Remove last item
        prior = prior[:-1]
        #Output back to user
        self.ids.calc_input.text = prior

    def posneg(self):
        #Create function to make textbox positive or negative
        prior = self.ids.calc_input.text
        #Test to check for negative
        if "-" in prior:
            self.ids.calc_input.text = f'{prior.replace("-","")}'
        else:
            self.ids.calc_input.text = f'-{prior}'



    def dot_button(self):
        prior = self.ids.calc_input.text
        if "." in prior:
            pass
        else:
            #Add a decimal point to the end
            prior = f"{prior}."
            #Output back to the textbox
            self.ids.calc_input.text = prior
    '''Math signs Button'''
    def math_sign(self,sign):
        #Create a variable that contains what was already in the Input box
        prior = self.ids.calc_input.text
        #Slap a plus sign to the text box
        self.ids.calc_input.text = f"{prior}{sign}"

    def equal(self):
        #Create a variable that contains what was already in the Input box
        prior = self.ids.calc_input.text

        #Error handling
        try:
            #Evaluate the math from the textbox
            answer = eval(prior)
            #Output the answer
            self.ids.calc_input.text = str(answer)
        except:
            self.ids.calc_input.text = 'Error'

class CalcApp(App):
    def build(self):
        Window.clearcolor = (0,0,0,1)
        return MyLayout()

if __name__ == "__main__":
    CalcApp().run()

