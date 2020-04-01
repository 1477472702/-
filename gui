from tkinter import *
from tkinter import ttk
from my_tru_table import true_table

class App(Frame):
    def __init__(self,master = None):
        Frame.__init__(self,master)
        self.pack()
        self.windows_init()
        self.v = StringVar()
        self.output = Entry(self.master,textvariable=self.v)
        self.output.place(x = 200,y = 150,width = 200)
        Label(self.master,text = '请输入逻辑表达式:').place(x = 95 ,y = 150)
        self.send = Button(self.master,text ='真值表', command=self.get_input)
        self.send.place(x = 200,y = 200,width = 50)
        self.out2 = Button(self.master,text = '卡诺图',command = self.get_cono)
        self.out2.place(x = 350,y=200,width = 50)
        self.master.mainloop()

    def windows_init(self):
        self.master.title('真值表与卡诺图')
        width, height = 600, 400
        self.master.geometry(str(width) + 'x' + str(height))
        Label(self.master,text = '目前仅支持大写字母\n否 ----------- `\n与 ----------- *\n或 ----------- +\n'
                                  + '同或 ----------- #\n' + '异或 ----------- &\n'+'异或 ----------- &\n'
                                + '卡诺图仅仅支持三变量或四变量').pack()

    def get_input(self):
        new = Tk()
        tr = ttk.Treeview(new)
        a = self.v.get()
        temp = true_table(a,flag=0)
        temp = temp.split('\n')
        temp1 = temp[0].split(' ')
        tr['columns'] = temp[0].split(' ')
        tr.pack()
        for i in range(len(temp1)):
            tr.heading(temp1[i],text=temp1[i])

        for i in range(1,len(temp)):
            tr.insert('',i,values=temp[i].split(' '))
            print(temp[i].split(' '))

        new.mainloop()

    def get_cono(self):
        new = Tk()
        tr = ttk.Treeview(new)
        a = self.v.get()
        temp = true_table(a, flag=1)
        temp = temp.split('\n')
        temp1 = temp[0].split(' ')
        tr['columns'] = temp[0].split(' ')
        tr.pack()
        for i in range(len(temp1)):
            tr.heading(temp1[i], text=temp1[i])

        for i in range(1, len(temp)):
            tr.insert('', i, values=temp[i].split(' '))
            print(temp[i].split(' '))

        new.mainloop()


if __name__ == '__main__':
    app = App()
    app.mainloop()

