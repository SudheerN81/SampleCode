# Description : This module is used to segregate the number of parcels
#               into different racks and to send them to proper address
# input variables : numcou, racks
# output variables :
# Author : N.Sudheer
# Date : 20-Nov-2020

#Declaration of Global Variables
racks=0
numcou = 0
isCheck = True
#declareing Class
class tech_test:
    #Declaring Constructor
    def __init__(self):
        pass

    # Declaring User dedifiend Function to get proper inputs
    def get_racks(self):
        """

        :return:
        """
        # Using Exceptional Handleing to know the given input is right or wrong
        try:
                # To get proper inout
                numcou=int(input("Enter the number of parcels : "))
                # Check if the input is even or odd
                # if it is odd addind one more value to it to get even number
                if numcou % 2 != 0:
                    numcou += 1
                    # Dividing to get the number of racks
                    racks = numcou/2
                    isCheck = False
                else:
                    # Dividing to get the number of racks
                    racks = numcou /2
                    isCheck = True
                # Check just to know the racks or positive or not.
                # It is for furture pupose. If the number of racks are changed
                # need not to modify the below functionalty
                if int(racks) > -1:
                    self.fun_start(int(racks),numcou, isCheck)
        except ValueError as exp:
            # Added only one exception currently
            # Can add more exceptions and finally and else statement also
            print("Please enter proper integer value" + str(exp.args))


    def fun_start(self,racks,parcels,checkValue):
        """
        :param racks: Integer variable to get the number of racks
        :param parcels: Integer variable to get the number of parcels
        :return:
        """
        # intiating of local variables
        s = int(racks)
        # Declared local temparory variables by adding 1
        # as Python will consider everything from 0
        k = int(parcels/2+1)
        temp = str(k)
        # looping the number of racks
        for index in range(racks,0,-1):
            # Getting the String Variable
            str1 = "Level " + str(index)
            if k == parcels and checkValue is False:
                temp = " "
            # Print the Value
            print(str1 + "     " + str(s) + "      " + str(temp))
            # Decresing the value of racks
            s-=1
            # Incresing the temparory variables value of number of parcels.
            k += 1
            temp = str(k)

# Created the Object of the class
Tech_Test_obj=tech_test()
# To execute main method
Tech_Test_obj.get_racks()
