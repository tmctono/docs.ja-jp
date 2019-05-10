---
title: '方法: オブジェクトのデータを書き込む XML ファイル (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
ms.openlocfilehash: 17f8463a4b905028d37a2e005562867f87f4bd2b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624357"
---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a><span data-ttu-id="9b425-102">方法: オブジェクトのデータを書き込む XML ファイル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b425-102">How to: Write Object Data to an XML File (Visual Basic)</span></span>
<span data-ttu-id="9b425-103"><xref:System.Xml.Serialization.XmlSerializer> クラスを使用して、クラスから XML ファイルにオブジェクトを書き込む例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9b425-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b425-104">例</span><span class="sxs-lookup"><span data-stu-id="9b425-104">Example</span></span>  
  
```vb  
Public Module XMLWrite  
  
    Sub Main()  
        WriteXML()  
    End Sub  
  
    Public Class Book  
        Public Title As String  
    End Class  
  
    Public Sub WriteXML()  
        Dim overview As New Book  
        overview.Title = "Serialization Overview"  
        Dim writer As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
        Dim file As New System.IO.StreamWriter(  
            "c:\temp\SerializationOverview.xml")  
        writer.Serialize(file, overview)  
        file.Close()  
    End Sub  
End Module  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9b425-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="9b425-105">Compiling the Code</span></span>  
 <span data-ttu-id="9b425-106">クラスには、パラメーターのないパブリック コンストラクターが必要です。</span><span class="sxs-lookup"><span data-stu-id="9b425-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9b425-107">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="9b425-107">Robust Programming</span></span>  
 <span data-ttu-id="9b425-108">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9b425-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="9b425-109">シリアル化されるクラスにパブリックなパラメーターなしのコンストラクターがない場合</span><span class="sxs-lookup"><span data-stu-id="9b425-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="9b425-110">ファイルが存在するものの、読み取り専用の場合 (<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="9b425-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="9b425-111">パスが長すぎる (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="9b425-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="9b425-112">ディスクの空き領域がない場合 (<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="9b425-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9b425-113">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="9b425-113">.NET Framework Security</span></span>  
 <span data-ttu-id="9b425-114">次のコード例では、ファイルが存在しない場合は新規にファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9b425-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="9b425-115">アプリケーションでファイルを作成する必要がある場合、そのアプリケーションにはフォルダーに対する `Create` アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="9b425-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="9b425-116">ファイルが既に存在する場合、アプリケーションに必要なのは、より低い権限である `Write` アクセスだけです。</span><span class="sxs-lookup"><span data-stu-id="9b425-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="9b425-117">フォルダーに対して `Read` アクセスを許可するのではなく、可能な限りアプリケーションの配置時にファイルを作成しておき、1 つのファイルに対してのみ `Create` アクセスを許可する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="9b425-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b425-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b425-118">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="9b425-119">方法: XML ファイル (Visual Basic) からオブジェクト データを読み込む</span><span class="sxs-lookup"><span data-stu-id="9b425-119">How to: Read Object Data from an XML File (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="9b425-120">シリアル化 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b425-120">Serialization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
