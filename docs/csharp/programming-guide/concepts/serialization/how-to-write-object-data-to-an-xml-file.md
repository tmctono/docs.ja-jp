---
title: XML ファイルにオブジェクト データを書き込む方法 (C#)
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: f7ffb47a22d3cd94cd7cb6f702b64180a8790eb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167513"
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a><span data-ttu-id="7e483-102">XML ファイルにオブジェクト データを書き込む方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="7e483-102">How to write object data to an XML file (C#)</span></span>
<span data-ttu-id="7e483-103"><xref:System.Xml.Serialization.XmlSerializer> クラスを使用して、クラスから XML ファイルにオブジェクトを書き込む例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7e483-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e483-104">例</span><span class="sxs-lookup"><span data-stu-id="7e483-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="7e483-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="7e483-105">Compiling the Code</span></span>  
 <span data-ttu-id="7e483-106">シリアル化されるクラスには、パラメーターのないパブリック コンストラクターが必要です。</span><span class="sxs-lookup"><span data-stu-id="7e483-106">The class being serialized must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7e483-107">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="7e483-107">Robust Programming</span></span>  
 <span data-ttu-id="7e483-108">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e483-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="7e483-109">シリアル化されるクラスにパブリックなパラメーターなしのコンストラクターがない場合</span><span class="sxs-lookup"><span data-stu-id="7e483-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="7e483-110">ファイルが存在するものの、読み取り専用の場合 (<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="7e483-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="7e483-111">パスが長すぎる (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="7e483-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="7e483-112">ディスクの空き領域がない場合 (<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="7e483-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7e483-113">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="7e483-113">.NET Framework Security</span></span>  
 <span data-ttu-id="7e483-114">次のコード例では、ファイルが存在しない場合は新規にファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e483-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="7e483-115">アプリケーションでファイルを作成する必要がある場合、そのアプリケーションにはフォルダーに対する `Create` アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7e483-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="7e483-116">ファイルが既に存在する場合、アプリケーションに必要なのは、より低い権限である `Write` アクセスだけです。</span><span class="sxs-lookup"><span data-stu-id="7e483-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="7e483-117">フォルダーに対して `Read` アクセスを許可するのではなく、可能な限りアプリケーションの配置時にファイルを作成しておき、1 つのファイルに対してのみ `Create` アクセスを許可する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="7e483-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e483-118">参照</span><span class="sxs-lookup"><span data-stu-id="7e483-118">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="7e483-119">XML ファイルからオブジェクト データを読み取る方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="7e483-119">How to read object data from an XML file (C#)</span></span>](./how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="7e483-120">シリアル化 (C#)</span><span class="sxs-lookup"><span data-stu-id="7e483-120">Serialization (C#)</span></span>](./index.md)
