---
title: '方法 : アプリケーション スコープのリソース ディクショナリを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 5bfb3ed0304598a5acf4b7682bf4a4169c5153d1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459799"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="6698b-102">方法 : アプリケーション スコープのリソース ディクショナリを使用する</span><span class="sxs-lookup"><span data-stu-id="6698b-102">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="6698b-103">この例では、アプリケーション スコープのカスタム リソース ディクショナリを定義して、使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6698b-103">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6698b-104">例</span><span class="sxs-lookup"><span data-stu-id="6698b-104">Example</span></span>  
 <span data-ttu-id="6698b-105"><xref:System.Windows.Application> は、<xref:System.Windows.Application.Resources%2A>共有リソースのアプリケーションスコープストアを公開します。</span><span class="sxs-lookup"><span data-stu-id="6698b-105"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="6698b-106">既定では、<xref:System.Windows.Application.Resources%2A> プロパティは <xref:System.Windows.ResourceDictionary> の型のインスタンスで初期化されます。</span><span class="sxs-lookup"><span data-stu-id="6698b-106">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="6698b-107"><xref:System.Windows.Application.Resources%2A>を使用してアプリケーションスコープのプロパティを取得および設定するときに、このインスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6698b-107">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="6698b-108">詳細については、「[方法: アプリケーションスコープのリソースを取得して設定する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6698b-108">For more information, see [How to: Get and Set an Application-Scope Resource](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span></span>
  
 <span data-ttu-id="6698b-109"><xref:System.Windows.Application.Resources%2A>を使用して複数のリソースを設定する場合は、代わりにカスタムリソースディクショナリを使用してそれらのリソースを格納し、代わりに <xref:System.Windows.Application.Resources%2A> を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="6698b-109">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="6698b-110">次に、XAML を使用してカスタムリソースディクショナリを宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6698b-110">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="6698b-111"><xref:System.Windows.Application.Resources%2A> を使用してリソースディクショナリ全体をスワップすると、アプリケーションスコープのテーマをサポートできます。各テーマは、1つのリソースディクショナリでカプセル化されます。</span><span class="sxs-lookup"><span data-stu-id="6698b-111">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="6698b-112"><xref:System.Windows.ResourceDictionary> を設定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="6698b-112">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="6698b-113">XAML で <xref:System.Windows.Application.Resources%2A> によって公開されているリソースディクショナリからアプリケーションスコープリソースを取得する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6698b-113">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="6698b-114">コードでリソースも取得する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6698b-114">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="6698b-115"><xref:System.Windows.Application.Resources%2A>を使用する場合は、2つの点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6698b-115">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="6698b-116">まず、ディクショナリ*キー*はオブジェクトであるため、プロパティ値を設定して取得するときは、まったく同じオブジェクトインスタンスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6698b-116">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="6698b-117">(文字列を使用する場合、キーは大文字と小文字が区別されることに注意してください)。2つ目は、ディクショナリ*値*がオブジェクトであるため、プロパティ値を取得するときに、値を目的の型に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6698b-117">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6698b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6698b-118">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [<span data-ttu-id="6698b-119">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="6698b-119">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="6698b-120">マージされたリソース ディクショナリ</span><span class="sxs-lookup"><span data-stu-id="6698b-120">Merged Resource Dictionaries</span></span>](../advanced/merged-resource-dictionaries.md)
