---
title: XML ファイルにオブジェクト データを書き込む方法 (C#)
description: この C# の例では、XmlSerializer クラスを使用して、クラスから XML ファイルにオブジェクトを書き込みます。 コードをコンパイルする方法について説明します。
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: c88a85f8bc65a195f404dab6aa39675bac7e4f84
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303128"
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a>XML ファイルにオブジェクト データを書き込む方法 (C#)
<xref:System.Xml.Serialization.XmlSerializer> クラスを使用して、クラスから XML ファイルにオブジェクトを書き込む例を次に示します。  
  
## <a name="example"></a>例  
  
```csharp  
public class XMLWrite  
{  
  
   static void Main(string[] args)  
    {  
        WriteXML();  
    }  
  
    public class Book  
    {  
        public String title;
    }  
  
    public static void WriteXML()  
    {  
        Book overview = new Book();  
        overview.title = "Serialization Overview";  
        System.Xml.Serialization.XmlSerializer writer =
            new System.Xml.Serialization.XmlSerializer(typeof(Book));  
  
        var path = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments) + "//SerializationOverview.xml";  
        System.IO.FileStream file = System.IO.File.Create(path);  
  
        writer.Serialize(file, overview);  
        file.Close();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 シリアル化されるクラスには、パラメーターのないパブリック コンストラクターが必要です。  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 次の条件を満たす場合は、例外が発生する可能性があります。  
  
- シリアル化されるクラスにパブリックなパラメーターなしのコンストラクターがない場合  
  
- ファイルが存在するものの、読み取り専用の場合 (<xref:System.IO.IOException>)  
  
- パスが長すぎる (<xref:System.IO.PathTooLongException>)。  
  
- ディスクの空き領域がない場合 (<xref:System.IO.IOException>)  
  
## <a name="net-security"></a>.NET セキュリティ  
 次のコード例では、ファイルが存在しない場合は新規にファイルを作成します。 アプリケーションでファイルを作成する必要がある場合、そのアプリケーションにはフォルダーに対する `Create` アクセスが必要です。 ファイルが既に存在する場合、アプリケーションに必要なのは、より低い権限である `Write` アクセスだけです。 フォルダーに対して `Read` アクセスを許可するのではなく、可能な限りアプリケーションの配置時にファイルを作成しておき、1 つのファイルに対してのみ `Create` アクセスを許可する方が安全です。  
  
## <a name="see-also"></a>関連項目

- <xref:System.IO.StreamWriter>
- [XML ファイルからオブジェクト データを読み取る方法 (C#)](./how-to-read-object-data-from-an-xml-file.md)
- [シリアル化 (C#)](./index.md)
