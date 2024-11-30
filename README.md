# big-data-DDL-

![image](https://github.com/user-attachments/assets/cf2f03dd-9ee7-4ad7-ab28-aa3fa2bd40bc)

![image](https://github.com/user-attachments/assets/0eba768a-d1f4-406f-a4e0-f4d4881688b4)

          CREATE TABLE Tabel_Faktur (  
              No_Faktur VARCHAR(50) PRIMARY KEY,                  
              Tanggal DATE NOT NULL,                             
              Id_Karyawan VARCHAR(50) NOT NULL,                 
              Nama_Pelanggan VARCHAR(100) NOT NULL,             
              Alamat_Pelanggan VARCHAR(255) NOT NULL,           
              No_Telp VARCHAR(20),                              
              Email_Pelanggan VARCHAR(100),                     
              FOREIGN KEY (Id_Karyawan) REFERENCES Karyawan(Id_Karyawan)
          );

![image](https://github.com/user-attachments/assets/3e50cf8a-0fbd-47cb-9da2-35933b92ffdd)
  
            CREATE TABLE Tabel_Karyawan (  
                Id_Karyawan VARCHAR(50) PRIMARY KEY,
                Nama_Karyawan VARCHAR(100) NOT NULL,
                Tempat_Lahir VARCHAR(100) NOT NULL, 
                Tgl_Lahir DATE NOT NULL,            
                Alamat VARCHAR(255) NOT NULL,       
                Jenis_Kelamin CHAR(1) CHECK (Jenis_Kelamin IN ('L', 'P')),
                Nama_Jabatan VARCHAR(100) NOT NULL,                  
                FOREIGN KEY (Nama_Jabatan) REFERENCES Jabatan(Nama_Jabatan)
            );

![image](https://github.com/user-attachments/assets/68009086-0d8c-4b8e-bd62-1ecc91d29f50)
             
              
                  CREATE TABLE Table_Jabatan (  
                      Nama_Jabatan VARCHAR(100) PRIMARY KEY,
                      Gaji_Pokok INT NOT NULL               
                  );

![image](https://github.com/user-attachments/assets/94bcd005-4cb9-41ea-a0af-e56c275b7af8)

            CREATE TABLE Tabel_Obat_Pelayanan (  
                Kode_Obat VARCHAR(50) PRIMARY KEY,                  
                Nama_Obat_Pelayanan VARCHAR(100) NOT NULL,          
                Harga_Satuan INT NOT NULL                           
            );
![image](https://github.com/user-attachments/assets/163a9d6e-fc97-4877-be21-857917c17278)
      
                CREATE TABLE Tabel_Detail_Transaksi (  
          No_Faktur VARCHAR(50),                              
          Kode_Obat VARCHAR(50),                              
          Jumlah INT NOT NULL,                                
          Subtotal INT NOT NULL,                              
          Diskon_Persen FLOAT,                                
          Total INT NOT NULL,                                 
          PRIMARY KEY (No_Faktur, Kode_Obat),                 
          FOREIGN KEY (No_Faktur) REFERENCES Faktur(No_Faktur),
          FOREIGN KEY (Kode_Obat) REFERENCES Obat_Pelayanan(Kode_Obat)
      );



![image](https://github.com/user-attachments/assets/32272d5a-5a99-40e4-a210-2635478208cb)
                  
                  
                  CREATE TABLE Total_Pembayaran (  
                      No_Faktur VARCHAR(50) PRIMARY KEY,                   
                      Subtotal INT NOT NULL,                               
                      Diskon_Total INT NOT NULL,                           
                      Total_Bayar INT NOT NULL,                            
                      FOREIGN KEY (No_Faktur) REFERENCES Faktur(No_Faktur) 
                  );
