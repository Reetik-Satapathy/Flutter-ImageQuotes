import 'dart:convert';
import 'package:flutter/material.dart';
import 'package:http/http.dart' as http;
// ignore_for_file: prefer_const_constructors

class Quotes extends StatefulWidget {
  const Quotes({super.key});

  @override
  State<Quotes> createState() => _QuotesState();
}

class _QuotesState extends State<Quotes> {
  String url = "https://generated.inspirobot.me/a/wGJgdNY4PQ.jpg";

  void fetch_url() async {
    Uri x=Uri.parse("https://sugoi-api.vercel.app/quotes");
    http.Response data=await http.get(x);
    dynamic parse= json.decode(data.body);

    setState(() {
      url=parse["url"];
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        centerTitle: true,
        title: Text(
          "Quotes from Famous People",
          style: TextStyle(color: Colors.white),
        ),
        backgroundColor: Colors.purple,
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Container(
              width: 300,
              height: 300,
              decoration: BoxDecoration(
                  image: DecorationImage(image: NetworkImage(url))
              ),
            ),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: fetch_url,
              child: Text("Generate Quote"),
              style: ElevatedButton.styleFrom(
                foregroundColor: Colors.white,
                backgroundColor: Colors.black,
              ),
            ),
          ],
        ),
      ),
    );
  }
}
