import 'package:flutter/material.dart';
import 'package:thirdapp/Indro.dart';
//import 'package:thirdapp/a1.dart';

void main() {
  runApp(Myapp());
}

class Myapp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: HomePage(),
      theme: ThemeData(
        primaryColor: Colors.blue,
        brightness: Brightness.light,
      ),
    );
  }
}

class HomePage extends StatefulWidget {
  @override
  State<HomePage> createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {
  var mytext = [FirstPage(), Information(), Services()];
  int setitem = 0;
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: Text('my name is amreshpal ares pa '),
        ),
        bottomNavigationBar: BottomNavigationBar(
          items: [
            BottomNavigationBarItem(icon: Icon(Icons.home), label: 'Home'),
            BottomNavigationBarItem(icon: Icon(Icons.info), label: 'About'),
            BottomNavigationBarItem(
                icon: Icon(Icons.cleaning_services), label: 'Clean'),
          ],
          currentIndex: setitem,
          onTap: (setvalue) {
            setState(() {
              setitem = setvalue;
            });
          },
        ),
        body: Center(child: mytext[setitem]));
  }
}

  
  import 'package:flutter/material.dart';

class FirstPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ListView(
      children: [
        ListTile(
          leading: Icon(Icons.abc_outlined),
          title: Text('this ia abc outline'),
        )
      ],
    );
  }
}

class Information extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Text("Information Page");
  }
}

class Services extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Text('Service Pages');
  }
}
