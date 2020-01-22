import csv
import os

while True :
  menu = ['1. Data barang', '2. Pencarian Barang', '3. Penjualan', '4.Stok']
  submenu1 = ['1.list barang', '2.input barang', '3.kembali ke menu utama','4.List harga terurut']
  DATABASE_FILE = 'database.csv'
  database = []


  #load data dari csv
  with open (DATABASE_FILE) as db_file:  
      csv_reader = csv.reader(db_file,delimiter=",") 
      for row in csv_reader : 
          database.append(row) 
      
      id_barang=int(database[len(database)-1][0])+1
      
  os.system("clear")
  print('\t'.join(menu)) 
  aksi = int (input ("pilihan: "))

  if aksi == 1:
    while True :
      print('\t'.join(submenu1))  #biar menjoin nya mentab submenu1
      aksiMenu1 = int (input ("pilih: "))
      
      if aksiMenu1 == 1:
          #menampilkan data dari array database
              print("%2s \t %10s \t %10s" %("ID","NAMA","HARGA"))
              
              for row in database : 
                print("%2s \t %10s \t %10s" %(row[0],row[1],row[2]))
                  #ngeprint buat format (2string) dulu teros diisi datanya
              print("")
          
      elif aksiMenu1 == 2 :
          with open (DATABASE_FILE, mode='a') as db_file :  
              csv_writer = csv.writer(db_file,quotechar='"')      
              while True :
                  nama_barang = input ("Masukkan Nama:")
                  if nama_barang =='=':
                      break
                  harga_barang = input ("Masukkan Harga:")
                  csv_writer.writerow([id_barang,nama_barang,harga_barang])
                  database.append([id_barang,nama_barang,harga_barang])
                  id_barang+=1
                  os.system("clear")
                  print ("Barang telah ditambahkan")
              
      elif aksiMenu1 == 3:
        break
      
      elif aksiMenu1 == 4:
        for data in range(len(database)):
          database[data][2]=int(database[data][2])

        a=len(database)
        for x in range(1,a,1):
          for y in range(x,0,-1):
            if database[y][2]<database[y-1][2]:
              temp=database[y]
              database[y]=database[y-1]
              database[y-1]=temp
        print("%2s \t %10s \t %10s" %("ID","NAMA","HARGA"))
        for row in database : 
                print("%2s \t %10s \t %10s" %(row[0],row[1],row[2]))
      else :
        print("salah input")
