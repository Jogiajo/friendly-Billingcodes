# friendly-Billingcodes
These are codes which help to to do some billing work 
from tkinter import*
import random
import time
import datetime

width = 1350
height = 650

root = Tk()
root.geometry(str(width)+"x" + str(height) + "+0+0")
root.title("FINE SPINNERS BILLING SYSTEM")

Tops = Frame(root, width=width, height=100, bd=8,relief='raise')
Tops.pack(side=TOP)

#main-frame
f1 = Frame(root, width=900, height=650, bd=8,relief='raise')
f1.pack(side=LEFT)
f2 = Frame(root, width=450, height=650, bd=8,relief='raise')
f2.pack(side=LEFT)
#sub-frame
f1a = Frame(f1, width=900, height=330, bd=8,relief='raise')
f1a.pack(side=TOP)
f2a = Frame(f1, width=900, height=320, bd=8,relief='raise')
f2a.pack(side=BOTTOM)

f1aa = Frame(f1a, width=400, height=430, bd=8,relief='raise')
f1aa.pack(side=LEFT)
f1ab = Frame(f1a, width=400, height=430, bd=8,relief='raise')
f1ab.pack(side=RIGHT)

f2aa = Frame(f2a, width=450, height=330, bd=8,relief='raise')
f2aa.pack(side=LEFT)
f2ab = Frame(f2a, width=450, height=330, bd=8,relief='raise')
f2ab.pack(side=LEFT)

lblInfo=Label(Tops, font=('arial',60,'bold'),text ="JOVIE BILLING SYSTEM", bd=10,anchor='w')
lblInfo.grid(row=0,column=0)

#============
# CALCULATOR
#============
#I should've defined all of the variables associated with StringVar() here

#calculator's screen
text_Input=StringVar()
operator=""

def btnClick(numbers):
	global operator
	operator = operator + str(numbers)
	text_Input.set(operator)

def btnClearDisplay():
	global operator
	operator=''
	text_Input.set('')

def btnEqualsInput():
	global operator
	sumup = str(eval(operator))
	text_Input.set(sumup)
	operator=''

#calculator's buttons
txtDisplay = Entry(f2,font=('arial',20,'bold'), textvariable=text_Input,bd=40, insertwidth=6, justify='right')
txtDisplay.grid(columnspan=4)
#----------------------------------------------------
btn7 = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='7',command=lambda:btnClick(7)).grid(row=1,column=0)
btn8 = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='8',command=lambda:btnClick(8)).grid(row=1,column=1)
btn9 = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='9',command=lambda:btnClick(9)).grid(row=1,column=2)
btnPlus = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='+',command=lambda:btnClick("+")).grid(row=1,column=3)
#----------------------------------------------------
btn4 = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='4',command=lambda:btnClick(4)).grid(row=2,column=0)
btn5 = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='5',command=lambda:btnClick(5)).grid(row=2,column=1)
btn6 = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='6',command=lambda:btnClick(6)).grid(row=2,column=2)
btnSub = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='-',command=lambda:btnClick("-")).grid(row=2,column=3)
#----------------------------------------------------
btn1 = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='1',command=lambda:btnClick(1)).grid(row=3,column=0)
btn2 = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='2',command=lambda:btnClick(2)).grid(row=3,column=1)
btn3 = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='3',command=lambda:btnClick(3)).grid(row=3,column=2)
btnMult = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='*',command=lambda:btnClick("*")).grid(row=3,column=3)
#----------------------------------------------------
btn0 = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='0',command=lambda:btnClick(0)).grid(row=4,column=0)
btnClear = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='c',command=btnClearDisplay).grid(row=4,column=1)
btnEqual = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='=',command=btnEqualsInput).grid(row=4,column=2)
btnDiv = Button(f2,padx=16,pady=16,bd=8,fg='black',font=('arial',20,'bold'),text='/',command=lambda:btnClick("/")).grid(row=4,column=3)

#==============
# ORDER's INFO
#==============
PaymentRef=StringVar()
REDSHIRTS=StringVar()
BLUESHIRTS=StringVar()
BLACKSHIRTS=StringVar()
WHITESHIRTS=StringVar()

REDSHIRTS.set(0)
BLUESHIRTS.set(0)
BLACKSHIRTS.set(0)
WHITESHIRTS.set(0)

lblRef = Label(f1aa,font=('arial',16,'bold'),text='Sales Reference',bd=16,justify='left')
lblRef.grid(row=0,column=0)
txtRef=Entry(f1aa,font=('arial',16,'bold'),textvariable=PaymentRef,bd=10,insertwidth=2,justify='left')
txtRef.grid(row=0,column=1)

lblREDSHIRTS = Label(f1aa,font=('arial',16,'bold'),text='REDSHIRTS',bd=16,justify='left')
lblREDSHIRTS.grid(row=1,column=0)
txtREDSHIRTS=Entry(f1aa,font=('arial',16,'bold'),textvariable=REDSHIRTS,bd=10,insertwidth=2,justify='left')
txtREDSHIRTS.grid(row=1,column=1)

lblBLUESHIRTS = Label(f1aa,font=('arial',16,'bold'),text='BLUESHIRTS',bd=16,justify='left')
lblBLUESHIRTS.grid(row=2,column=0)
txtBLUESHIRTS=Entry(f1aa,font=('arial',16,'bold'),textvariable=BLUESHIRTS,bd=10,insertwidth=2,justify='left')
txtBLUESHIRTS.grid(row=2,column=1)

lblBLACKSHIRTS = Label(f1aa,font=('arial',16,'bold'),text='BLACKSHIRTS',bd=16,justify='left')
lblBLACKSHIRTS.grid(row=3,column=0)
txtBLACKSHIRTS=Entry(f1aa,font=('arial',16,'bold'),textvariable=BLACKSHIRTS,bd=10,insertwidth=2,justify='left')
txtBLACKSHIRTS.grid(row=3,column=1)

lblWHITESHIRTS= Label(f1aa,font=('arial',16,'bold'),text='WHITESHIRTS',bd=16,justify='left')
lblWHITESHIRTS.grid(row=4,column=0)
txtWHITESHIRTS=Entry(f1aa,font=('arial',16,'bold'),textvariable=WHITESHIRTS,bd=10,insertwidth=2,justify='left')
txtWHITESHIRTS.grid(row=4,column=1)


#==============
# ORDER's COST
#==============
DateofOrder=StringVar()
COSTOFREDSHIRTS =StringVar()
COSTOFBLUESHIRTS=StringVar()
COSTOFBLACKSHIRTS=StringVar()
COSTOFWHITESHIRTS=StringVar()

DateofOrder.set(time.strftime("%d/%m/%y"))

lblDateofOrder = Label(f1ab,font=('arial',16,'bold'),text='Order Date',bd=16,anchor='w')
lblDateofOrder.grid(row=0,column=0)
txtDateofOrder=Entry(f1ab,font=('arial',16,'bold'),textvariable=DateofOrder,bd=10,insertwidth=2,justify='left')
txtDateofOrder.grid(row=0,column=1)

lblCOSTOFREDSHIRTS = Label(f1ab,font=('arial',16,'bold'),text='REDSHIRTSCOST',bd=16,anchor='w')
lblCOSTOFREDSHIRTS.grid(row=1,column=0)
txtCOSTOFREDSHIRTS=Entry(f1ab,font=('arial',16,'bold'),textvariable=COSTOFREDSHIRTS,bd=10,insertwidth=2,justify='left')
txtCOSTOFREDSHIRTS.grid(row=1,column=1)


lblCOSTOFBLUESHIRTS = Label(f1ab,font=('arial',16,'bold'),text='BLUESHIRTSCOST',bd=16,anchor='w')
lblCOSTOFBLUESHIRTS.grid(row=2,column=0)
txtCOSTOFBLUESHIRTS=Entry(f1ab,font=('arial',16,'bold'),textvariable=COSTOFBLUESHIRTS,bd=10,insertwidth=2,justify='left')
txtCOSTOFBLUESHIRTS.grid(row=2,column=1)

lblCOSTOFBLACKSHIRTS = Label(f1ab,font=('arial',16,'bold'),text='BLACKSHIRTSCOST',bd=16,anchor='w')
lblCOSTOFBLACKSHIRTS.grid(row=3,column=0)
txtCOSTOFBLACKSHIRTS=Entry(f1ab,font=('arial',16,'bold'),textvariable=COSTOFBLACKSHIRTS,bd=10,insertwidth=2,justify='left')
txtCOSTOFBLACKSHIRTS.grid(row=3,column=1)

lblCOSTOFWHITESHIRTS= Label(f1ab,font=('arial',16,'bold'),text='WHITESHIRTSCOST ',bd=16,anchor='w')
lblCOSTOFWHITESHIRTS.grid(row=4,column=0)
txtCOSTOFWHITESHIRTS=Entry(f1ab,font=('arial',16,'bold'),textvariable=COSTOFWHITESHIRTS,bd=10,insertwidth=2,justify='left')
txtCOSTOFWHITESHIRTS.grid(row=4,column=1)

#=================
# ORDER's SUMMARY
#=================
PaidTax=StringVar()
SubTotal=StringVar()
TotalCost=StringVar()

lblPaidTax = Label(f2aa,font=('arial',16,'bold'),text='Paid Tax',bd=8,anchor='w')
lblPaidTax.grid(row=2,column=0)
txtPaidTax = Entry(f2aa,font=('arial',16,'bold'),textvariable=PaidTax,bd=8,insertwidth=2,justify='left')
txtPaidTax.grid(row=2,column=1)

lblSubTotal = Label(f2aa,font=('arial',16,'bold'),text='Sub Total',bd=8,anchor='w')
lblSubTotal.grid(row=3,column=0)
txtSubTotal = Entry(f2aa,font=('arial',16,'bold'),textvariable=SubTotal,bd=8,insertwidth=2,justify='left')
txtSubTotal.grid(row=3,column=1)

lblTotalCost = Label(f2aa,font=('arial',16,'bold'),text='Total Cost',bd=8,anchor='w')
lblTotalCost.grid(row=4,column=0)
txtTotalCost = Entry(f2aa,font=('arial',16,'bold'),textvariable=TotalCost,bd=8,insertwidth=2,justify='left')
txtTotalCost.grid(row=4,column=1)

#=====================
# ORDER's INFO BUTTONS
#=====================
from tkinter import messagebox

def iExit():
	qExit = messagebox.askyesno("Billing system","Do you want to exit the system?")
	if qExit > 0:
		root.destroy()
		return

def Reset():
	PaymentRef.set("")
	REDSHIRTS.set(0)
	BLUESHIRTS.set(0)
	BLACKSHIRTS.set(0)
	WHITESHIRTS.set(0)
	PaidTax.set("")
	SubTotal.set("")
	TotalCost.set("")
	COSTOFREDSHIRTS.set("")
	COSTOFBLUESHIRTS.set("")
	COSTOFBLACKSHIRTS.set("")
	COSTOFWHITESHIRTS.set("")

def PayReference():
	x = random.randint(10034,699812)
	randomRef = str(x)
	PaymentRef.set("BILL"+randomRef)

def CostOfOrder():
	REDSHIRTSPRICE = float(REDSHIRTS.get())
	BLUESHIRTSPRICE = float(BLUESHIRTS.get())
	BLACKSHIRTSPRICE = float(BLACKSHIRTS.get())
	WHITESHIRTSPRICE = float(WHITESHIRTS.get())
	
	REDSHIRTSCOST = "shs " + str("%.2f"%((REDSHIRTSPRICE*15.49)))
	COSTOFREDSHIRTS.set(REDSHIRTSCOST)
	
	BLUESHIRTSCOST = "shs " + str("%.2f"%((BLUESHIRTSPRICE*7.49)))
	COSTOFBLUESHIRTS.set(BLUESHIRTSCOST)
	
	BLACKSHIRTSCOST = "shs " + str("%.2f"%((BLACKSHIRTSPRICE*5.50)))
	COSTOFBLACKSHIRTS.set(BLACKSHIRTSCOST)
	
	WHITESHIRTSCOST = "shs " + str("%.2f"%((WHITESHIRTSPRICE*4.50)))
	COSTOFWHITESHIRTS.set(WHITESHIRTSCOST)
	
	ToC = "shs " + str("%.2f"%((REDSHIRTSPRICE*15.49)+(BLUESHIRTSPRICE*7.49)+(BLACKSHIRTSPRICE*5.50)+(WHITESHIRTSPRICE*4.50)))
	SubTotal.set(ToC)
	
	Tax = "shs " + str("%.2f"%(((REDSHIRTSPRICE*15.49)+(BLUESHIRTSPRICE*7.49)+(BLACKSHIRTSPRICE*5.50)+(WHITESHIRTSPRICE*4.50))*0.2))
	PaidTax.set(Tax)
	
	TaxPay = (float((REDSHIRTSPRICE*15.49)+(BLUESHIRTSPRICE*7.49)+(BLACKSHIRTSPRICE*5.50)+(WHITESHIRTSPRICE*4.50))*0.2)
	Cost = ((REDSHIRTSPRICE*15.49)+(BLUESHIRTSPRICE*7.49)+(BLACKSHIRTSPRICE*5.50)+(WHITESHIRTSPRICE*4.50))
	CostofItems = "shs " + str("%.2f"%(TaxPay+Cost))
	TotalCost.set(CostofItems)
	
	x=random.randint(10034,699812)
	randomRef=str(x)
	PaymentRef.set("BILL"+randomRef)
		

btnTotal=Button(f2ab,padx=16,pady=16,bd=8,fg='black',font=('arial',16,'bold'),width=15,text='Total Cost', command = CostOfOrder).grid(row=0,column=0)

btnRefer=Button(f2ab,padx=16,pady=16,bd=8,fg='black',font=('arial',16,'bold'),width=15,text='Sales Reference', command=PayReference).grid(row=0,column=1)

btnReset=Button(f2ab,padx=16,pady=16,bd=8,fg='black',font=('arial',16,'bold'),width=15,text='Reset',command=Reset).grid(row=1,column=0)

btnExit=Button(f2ab,padx=16,pady=16,bd=8,fg='black',font=('arial',16,'bold'),width=15,text='Exit',command=iExit).grid(row=1,column=1)



root.mainloop()
