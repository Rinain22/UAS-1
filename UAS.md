# UAS-1
mport 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    debugShowCheckedModeBanner: false,
    title: 'Routing Navigation',
    initialRoute: '/',
    routes: {
      '/' : (context) => HalamanPertama(),
      HalamanKedua.routeName : (context) => HalamanKedua(),
      HalamanKetiga.routeName : (context) => HalamanKetiga(),
    },
  ));
}

class HalamanPertama extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Rina Indah Sari_UAS'),
      ),
      body: Center(
        child: ListView(
          children: <Widget>[
            RaisedButton(
              child: Text('Perhitungan'),
              onPressed: () {
                Navigator.pushNamed(context, HalamanKedua.routeName);
              },
            ),
            RaisedButton(
              child: Text('Data Lengkap'),
              onPressed: () {
                Navigator.pushReplacementNamed(context, HalamanKetiga.routeName);
              },
            ),
          ],
        ),
      ),
    );
  }
}

class HalamanKedua extends StatelessWidget {
  static const String routeName = "/halamanKedua";
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Perhitungan"),
        ),
      
      
      body: Center(
        child: RaisedButton(
          child: Text('Kembali ke halaman utama'),
          onPressed: () {
            Navigator.pop(context);
          },
        ),
      ),
    );
  }
}

class HalamanKetiga extends StatelessWidget {
  static const String routeName = "/halamanKetiga";
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Data Lengkap"),
        
      ),
      body: ListView(children: <Widget>[
        Center(
            child: Text('Data Mahasiswa',
                style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold))),
        DataTable(
          columns: [
            DataColumn(label: Text('NIRM')),
            DataColumn(label: Text('Nama Mahasiswa')),
            DataColumn(label: Text('Program Studi')),
            DataColumn(label: Text('Kelas')),
          ],
          rows: [
            DataRow(cells: [
              DataCell(Text('2018020663')),
              DataCell(Text('Rina indah Sari')),
              DataCell(Text('Sistem Informasi')),
              DataCell(Text('6SIA11')),
  
            ]),
          ],
        ),
      ]),
    );
  }
}
