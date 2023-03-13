import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'César Escobar',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Color.fromARGB(255, 246, 2, 2)),
        useMaterial3: true,
      ),
      home: const MyHomePage(title: 'Operadores Básicos'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});
  final String title;
  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  double _counter = 10;

  void _incrementCounter() {
    setState(() {
      _counter += 2;
    });
  }
  void _decrementCounter() {
    setState(() {
      _counter -= 2;
    });
  }
  void _multiplierCounter() {
    setState(() {
      _counter *= 2;
    });
  }
  void _divisorCounter() {
    setState(() {
      _counter /= 2;
    });
  }
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Theme.of(context).colorScheme.inversePrimary,
        title: Text(widget.title),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            const Text(
              'Contador:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
          ],
        ),
      ),
      
      floatingActionButton: Row(
        children: [
          FloatingActionButton(
            onPressed: _incrementCounter,
            tooltip: 'Sumar',
            child: Row(
              mainAxisSize: MainAxisSize.min,
              children: [
                const Icon(Icons.add),
                const SizedBox(width: 3),
                const Text('2'),
              ],
            ),
          ),
          FloatingActionButton(
            onPressed: _decrementCounter,
            tooltip: 'Restar',
            child: Row(
              mainAxisSize: MainAxisSize.min,
              children: [
                const Icon(Icons.remove),
                const SizedBox(width: 3),
                const Text('2'),
              ],
            ),
          ),
          FloatingActionButton(
            onPressed: _multiplierCounter,
            tooltip: 'Multiplicar',
            child: Row(
              mainAxisSize: MainAxisSize.min,
              children: [
                const Icon(Icons.close),
                const SizedBox(width: 3),
                const Text('2'),
              ],
            ),
          ),
          FloatingActionButton(
            onPressed: _divisorCounter,
            tooltip: 'Dividir',
            child: Row(
              mainAxisSize: MainAxisSize.min,
              children: [
                const Icon(Icons.close),
                const SizedBox(width: 3),
                const Text('1/2'),
              ],
            ),
          ),
        ],
      )
    );
  }
}
