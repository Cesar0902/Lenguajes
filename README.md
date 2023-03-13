# Lenguajes
Lenguajes de programacion - César Escobar
import 'package:flutter/material.dart';

void main() => runApp(ContadorApp());

class ContadorApp extends StatefulWidget {
  @override
  _ContadorAppState createState() => _ContadorAppState();
}

class _ContadorAppState extends State<ContadorApp> {
  int contador = 10;

  void sumar() {
    setState(() {
      contador += 2;
    });
  }

  void restar() {
    setState(() {
      contador -= 2;
    });
  }

  void multiplicar() {
    setState(() {
      contador *= 2;
    });
  }

  void dividir() {
    setState(() {
      contador ~/= 2;
    });
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        appBar: AppBar(
          title: Text('César Fernando Escobar Perdomo'),
        ),
        body: Center(
          child: Text(
            '$contador',
            style: TextStyle(fontSize: 50.0),
          ),
        ),
        floatingActionButton: Row(
          mainAxisAlignment: MainAxisAlignment.spaceAround,
          children: <Widget>[
            FloatingActionButton(
              onPressed: sumar,
              child: Icon(Icons.add),
            ),
            FloatingActionButton(
              onPressed: restar,
              child: Icon(Icons.remove),
            ),
            FloatingActionButton(
              onPressed: multiplicar,
              child: Icon(Icons.clear),
            ),
            FloatingActionButton(
              onPressed: dividir,
              child: Icon(Icons.star),
            ),
          ],
        ),
      ),
    );
  }
}
