- user.dart
~~~~
import 'dart:convert' as convert;

class User {
  String? nombre;
  String? avatar;
  String? email;

  User(String json) {
    final jsonResponse = convert.jsonDecode(json);
    nombre = jsonResponse["data"]["firstname"];
    avatar = jsonResponse["data"]["avatar"];
    email = jsonResponse["data"]["email"];
  }
}

~~~~

- main.dart

~~~~
import 'package:flutter/material.dart';
import 'models/user.dart';
import 'package:http/http.dart' as http;
import 'widget/template.dart';

void main() => runApp(Sena());

class Sena extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Mi App',
      home: Scaffold(
          appBar: AppBar(title: Text('Inicio')),
          body: FutureBuilder<User>(
            future: getUser(),
            builder: (context, snapshot) {
              if (snapshot.connectionState == ConnectionState.done) {
                User user = snapshot.data as User;
                return Template(user: user);
              }
              return Center(child: CircularProgressIndicator());
            },
          )),
    );
  }

  Future<User> getUser() async {
    final url = Uri.https('reqres.in', '/api/users/2');
    final response = await http.get(url);
    return User(response.body);
  }
}

~~~~

- template.dart

~~~~

import 'package:flutter/material.dart';
import '../models/user.dart';

class Template extends StatelessWidget {
  const Template({
    Key? key,
    required this.user,
  }) : super(key: key);

  final User user;

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        SizedBox(height: 15.0),
        Text(
          user.email!,
          style: TextStyle(fontSize: 20.0),
        ),
        SizedBox(height: 15.0),
        Image(
          image: NetworkImage(
            user.avatar!,
          ),
        ),
        SizedBox(height: 15.0),
        Text(
          user.email!,
          style: TextStyle(fontSize: 20.0),
        ),
        SizedBox(height: 15.0),
        Row(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: [
            Icon(
              Icons.facebook,
              color: Colors.blue,
              size: 24.0,
              semanticLabel: 'Text to announce in accessibility modes',
            ),
            Icon(
              Icons.message,
              color: Colors.blue,
              size: 30.0,
            ),
            Icon(
              Icons.maps_home_work,
              color: Colors.blue,
              size: 36.0,
            ),
          ],
        )
      ],
    );
  }
}


~~~~
