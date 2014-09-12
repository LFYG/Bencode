Bencode
======================

Description
----------------------

Bencode can decode a byte array into C# object, dictionary, list, int and string types. It also can package abvoe types into a byte array.

Get more information about [Bencode in Wikipedia](http://en.wikipedia.org/wiki/Bencode).

Installation
----------------------

You can start using Bencode right away by installing the [NuGet package](https://nuget.org/packages/NReadability):

[![PM&gt; Install-Package Bencode](http://images.cnitblog.com/blog/70278/201409/121639165594283.jpg)](https://www.nuget.org/packages/Bencode/)

Gettging Started
----------------------

In order to encode objects to a byte array:

```c#
Dictionary<string, object> dic = new Dictionary<string, Object>
    {
        {"nick", "Create Chen"},
        {"blog","http://www.cnblogs.com/technology"},
        {"interests", new List<object> {"coding", "basketball"}}
    };
byte[] bytes = BencodeUtility.Encode(dic).ToArray();

string str = Encoding.ASCII.GetString(bytes);
Console.WriteLine(str);
```

Decode a byte array contains following methods:
* BencodeUtility.Decode(byte[] source)
* BencodeUtility.DecodeInt(byte[] source)
* BencodeUtility.DecodeString(byte[] source)
* BencodeUtility.DecodeList(byte[] source)
* BencodeUtility.DecodeDicionary(byte[] source)