---
title: '方法: ジェネリック型 T が DataRow ではない CopyToDataTable<T> を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
ms.openlocfilehash: 6c14e87c5caede4fea52867d9f184f3f64a5ed3b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249644"
---
# <a name="how-to-implement-copytodatatablet-where-the-generic-type-t-is-not-a-datarow"></a><span data-ttu-id="20eb2-102">方法 : ジェネリック型 T\<がデータ行ではない場合> CopyToDataTable T を実装する</span><span class="sxs-lookup"><span data-stu-id="20eb2-102">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>
<span data-ttu-id="20eb2-103">データ バインドには、しばしば <xref:System.Data.DataTable> オブジェクトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="20eb2-103">The <xref:System.Data.DataTable> object is often used for data binding.</span></span> <span data-ttu-id="20eb2-104"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドは、クエリの結果を受け取り、そのデータを <xref:System.Data.DataTable> にコピーします。これをデータ バインディングに利用できます。</span><span class="sxs-lookup"><span data-stu-id="20eb2-104">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method takes the results of a query and copies the data into a <xref:System.Data.DataTable>, which can then be used for data binding.</span></span> <span data-ttu-id="20eb2-105">ただし、<xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドは、ジェネリック パラメーター <xref:System.Collections.Generic.IEnumerable%601> が `T` 型である <xref:System.Data.DataRow> ソースに対してのみ作用します。</span><span class="sxs-lookup"><span data-stu-id="20eb2-105">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> methods, however, only operate on an <xref:System.Collections.Generic.IEnumerable%601> source where the generic parameter `T` is of type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="20eb2-106">有用ではありますが、一連のスカラー型、匿名型を射影するクエリ、またはテーブルの結合を実行するクエリからは、テーブルを作成できません。</span><span class="sxs-lookup"><span data-stu-id="20eb2-106">Although this is useful, it does not allow tables to be created from a sequence of scalar types, from queries that project anonymous types, or from queries that perform table joins.</span></span>  
  
 <span data-ttu-id="20eb2-107">このトピックでは、`CopyToDataTable<T>` 型以外のジェネリック パラメーター `T` を受け取る 2 つのカスタム <xref:System.Data.DataRow> 拡張メソッドを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="20eb2-107">This topic describes how to implement two custom `CopyToDataTable<T>` extension methods that accept a generic parameter `T` of a type other than <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="20eb2-108"><xref:System.Data.DataTable> ソースから <xref:System.Collections.Generic.IEnumerable%601> を作成するロジックは、`ObjectShredder<T>` クラスに存在し、オーバーロードされた 2 つの `CopyToDataTable<T>` 拡張メソッドにラップされています。</span><span class="sxs-lookup"><span data-stu-id="20eb2-108">The logic to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source is contained in the `ObjectShredder<T>` class, which is then wrapped in two overloaded `CopyToDataTable<T>` extension methods.</span></span> <span data-ttu-id="20eb2-109">`Shred` クラスの `ObjectShredder<T>` メソッドは、データが格納された <xref:System.Data.DataTable> を返し、<xref:System.Collections.Generic.IEnumerable%601> ソース、<xref:System.Data.DataTable>、および <xref:System.Data.LoadOption> 列挙型の 3 つの入力パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="20eb2-109">The `Shred` method of the `ObjectShredder<T>` class returns the filled <xref:System.Data.DataTable> and accepts three input parameters: an <xref:System.Collections.Generic.IEnumerable%601> source, a <xref:System.Data.DataTable>, and a <xref:System.Data.LoadOption> enumeration.</span></span> <span data-ttu-id="20eb2-110">返される <xref:System.Data.DataTable> の最初のスキーマは、`T` 型のスキーマに基づきます。</span><span class="sxs-lookup"><span data-stu-id="20eb2-110">The initial schema of the returned <xref:System.Data.DataTable> is based on the schema of the type `T`.</span></span> <span data-ttu-id="20eb2-111">既存のテーブルを入力として指定する場合は、そのスキーマが、`T` 型のスキーマと矛盾がないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20eb2-111">If an existing table is provided as input, the schema must be consistent with the schema of the type `T`.</span></span> <span data-ttu-id="20eb2-112">返されたテーブルでは、`T` 型のパブリック プロパティおよびパブリック フィールドが、それぞれ <xref:System.Data.DataColumn> に変換されます。</span><span class="sxs-lookup"><span data-stu-id="20eb2-112">Each public property and field of the type `T` is converted to a <xref:System.Data.DataColumn> in the returned table.</span></span> <span data-ttu-id="20eb2-113">`T` から派生した型がソース シーケンスに含まれている場合は、返されるテーブルのスキーマが、あらゆる追加パブリック プロパティまたは追加パブリック フィールドに展開されます。</span><span class="sxs-lookup"><span data-stu-id="20eb2-113">If the source sequence contains a type derived from `T`, the returned table schema is expanded for any additional public properties or fields.</span></span>  
  
 <span data-ttu-id="20eb2-114">カスタム `CopyToDataTable<T>` メソッドの使用例については、[クエリから DataTable を作成する](creating-a-datatable-from-a-query-linq-to-dataset.md)方法に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20eb2-114">For examples of using the custom `CopyToDataTable<T>` methods, see [Creating a DataTable From a Query](creating-a-datatable-from-a-query-linq-to-dataset.md).</span></span>  
  
### <a name="to-implement-the-custom-copytodatatablet-methods-in-your-application"></a><span data-ttu-id="20eb2-115">カスタム CopyToDataTable\<T> メソッドをアプリケーションに実装するには</span><span class="sxs-lookup"><span data-stu-id="20eb2-115">To implement the custom CopyToDataTable\<T> methods in your application</span></span>  
  
1. <span data-ttu-id="20eb2-116">`ObjectShredder<T>` クラスを実装して、<xref:System.Data.DataTable> ソースから <xref:System.Collections.Generic.IEnumerable%601> を作成します。</span><span class="sxs-lookup"><span data-stu-id="20eb2-116">Implement the `ObjectShredder<T>` class to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  

    <span data-ttu-id="20eb2-117">前の例では、 のプロパティ`DataColumn`が null 許容値型ではないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="20eb2-117">The preceding example assumes that the properties of the `DataColumn` are not nullable value types.</span></span> <span data-ttu-id="20eb2-118">null 許容値型のプロパティを処理するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="20eb2-118">To handle properties with nullable value types, use the following code:</span></span>

    ```csharp
    DataColumn dc = table.Columns.Contains(p.Name) ? table.Columns[p.Name] : table.Columns.Add(p.Name, Nullable.GetUnderlyingType(p.PropertyType) ?? p.PropertyType);
    ```

2. <span data-ttu-id="20eb2-119">カスタム `CopyToDataTable<T>` 拡張メソッドをクラスに実装します。</span><span class="sxs-lookup"><span data-stu-id="20eb2-119">Implement the custom `CopyToDataTable<T>` extension methods in a class:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3. <span data-ttu-id="20eb2-120">`ObjectShredder<T>` クラスおよび `CopyToDataTable<T>` 拡張メソッドをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="20eb2-120">Add the `ObjectShredder<T>` class and `CopyToDataTable<T>` extension methods to your application.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        ' Your application code using CopyToDataTable<T>.  
    End Sub  
End Module  
  
Public Module CustomLINQtoDataSetMethods  
…  
End Module  
  
Public Class ObjectShredder(Of T)  
…  
End Class
```
  
```csharp
class Program  
{  
    static void Main(string[] args)  
    {  
        // Your application code using CopyToDataTable<T>.  
    }  
}  
public static class CustomLINQtoDataSetMethods  
{  
…  
}  
public class ObjectShredder<T>  
{  
…  
}  
```
  
## <a name="see-also"></a><span data-ttu-id="20eb2-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="20eb2-121">See also</span></span>

- [<span data-ttu-id="20eb2-122">クエリによる DataTable の作成</span><span class="sxs-lookup"><span data-stu-id="20eb2-122">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)
- [<span data-ttu-id="20eb2-123">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="20eb2-123">Programming Guide</span></span>](programming-guide-linq-to-dataset.md)
