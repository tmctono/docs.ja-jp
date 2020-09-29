---
title: My.WebServices オブジェクト
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: 0b63b44c2cd9d55094fb83fed6c04e4de528a25c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867198"
---
# <a name="mywebservices-object"></a><span data-ttu-id="1347f-102">My.WebServices オブジェクト</span><span class="sxs-lookup"><span data-stu-id="1347f-102">My.WebServices Object</span></span>

<span data-ttu-id="1347f-103">現在のプロジェクトによって参照される各 XML Web サービスの単一のインスタンスを作成してアクセスするためのプロパティを提供します。</span><span class="sxs-lookup"><span data-stu-id="1347f-103">Provides properties for creating and accessing a single instance of each XML Web service referenced by the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1347f-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="1347f-104">Remarks</span></span>  

 <span data-ttu-id="1347f-105">`My.WebServices` オブジェクトは、現在のプロジェクトにより参照されている各 Web サービスのインスタンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1347f-105">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="1347f-106">各インスタンスは要求に応じてインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="1347f-106">Each instance is instantiated on demand.</span></span> <span data-ttu-id="1347f-107">これらの Web サービスには `My.WebServices` オブジェクトのプロパティを介してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1347f-107">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="1347f-108">プロパティの名前は、プロパティがアクセスする Web サービスの名前と同じになります。</span><span class="sxs-lookup"><span data-stu-id="1347f-108">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="1347f-109"><xref:System.Web.Services.Protocols.SoapHttpClientProtocol> から継承されたクラスはすべて Web サービスです。</span><span class="sxs-lookup"><span data-stu-id="1347f-109">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span> <span data-ttu-id="1347f-110">プロジェクトへの Web サービスの追加の詳細については、「[アプリケーションの Web サービスへのアクセス](../../developing-apps/programming/accessing-application-web-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1347f-110">For information about adding Web services to a project, see [Accessing Application Web Services](../../developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="1347f-111">`My.WebServices` オブジェクトでは、現在のプロジェクトに関連付けられている Web サービスのみが公開されます。</span><span class="sxs-lookup"><span data-stu-id="1347f-111">The `My.WebServices` object exposes only the Web services associated with the current project.</span></span> <span data-ttu-id="1347f-112">参照されている DLL で宣言されている Web サービスへのアクセスは提供されません。</span><span class="sxs-lookup"><span data-stu-id="1347f-112">It does not provide access to Web services declared in referenced DLLs.</span></span> <span data-ttu-id="1347f-113">DLL で提供されている Web サービスにアクセスするには、Web サービスの修飾名を *DllName*.*WebServiceName* の形式で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1347f-113">To access a Web service that a DLL provides, you must use the qualified name of the Web service, in the form *DllName*.*WebServiceName*.</span></span> <span data-ttu-id="1347f-114">詳細については、「[アプリケーションの Web サービスへのアクセス](../../developing-apps/programming/accessing-application-web-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1347f-114">For more information, see [Accessing Application Web Services](../../developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="1347f-115">オブジェクトとそのプロパティは、Web アプリケーションで使用できません。</span><span class="sxs-lookup"><span data-stu-id="1347f-115">The object and its properties are not available for Web applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1347f-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1347f-116">Properties</span></span>  

 <span data-ttu-id="1347f-117">`My.WebServices` オブジェクトの各プロパティにより、現在のプロジェクトで参照されている Web サービスのインスタンスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1347f-117">Each property of the `My.WebServices` object provides access to an instance of a Web service referenced by the current project.</span></span> <span data-ttu-id="1347f-118">プロパティの名前は、プロパティがアクセスする Web サービスの名前と同じになり、プロパティの型は Web サービスの型と同じになります。</span><span class="sxs-lookup"><span data-stu-id="1347f-118">The name of the property is the same as the name of the Web service that the property accesses, and the property type is the same as the Web service's type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1347f-119">名前の競合がある場合、Web サービスにアクセスするためのプロパティ名は、*RootNamespace*_*Namespace*\_*ServiceName* になります。</span><span class="sxs-lookup"><span data-stu-id="1347f-119">If there is a name collision, the property name for accessing a Web service is *RootNamespace*_*Namespace*\_*ServiceName*.</span></span> <span data-ttu-id="1347f-120">たとえば、`Service1` という名前の 2 つの Web サービスがあるとします。</span><span class="sxs-lookup"><span data-stu-id="1347f-120">For example, consider two Web services named `Service1`.</span></span> <span data-ttu-id="1347f-121">これらのサービスのいずれかがルート名前空間 `WindowsApplication1` および名前空間 `Namespace1` にある場合は、`My.WebServices.WindowsApplication1_Namespace1_Service1` を使用してそのサービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1347f-121">If one of these services is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that service by using `My.WebServices.WindowsApplication1_Namespace1_Service1`.</span></span>  
  
 <span data-ttu-id="1347f-122">`My.WebServices` オブジェクトのいずれかのプロパティに初めてアクセスすると、Web サービスの新しいインスタンスが作成され、保存されます。</span><span class="sxs-lookup"><span data-stu-id="1347f-122">When you first access one of the `My.WebServices` object's properties, it creates a new instance of the Web service and stores it.</span></span> <span data-ttu-id="1347f-123">そのプロパティのその後のアクセスでは、Web サービスのインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="1347f-123">Subsequent accesses of that property return that instance of the Web service.</span></span>  
  
 <span data-ttu-id="1347f-124">Web サービスを破棄するには、Web サービスのプロパティに `Nothing` を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1347f-124">You can dispose of a Web service by assigning `Nothing` to the property for that Web service.</span></span> <span data-ttu-id="1347f-125">プロパティ セッターによって、格納されている値に `Nothing` が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1347f-125">The property setter assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="1347f-126">プロパティに `Nothing` 以外の値を割り当てた場合、セッターが <xref:System.ArgumentException> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="1347f-126">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="1347f-127">`My.WebServices` オブジェクトのプロパティに Web サービスのインスタンスが格納されているかどうかをテストするには、`Is` または `IsNot` 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="1347f-127">You can test whether a property of the `My.WebServices` object stores an instance of the Web service by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="1347f-128">これらの演算子を使用すると、プロパティの値が `Nothing` かどうかをチェックできます。</span><span class="sxs-lookup"><span data-stu-id="1347f-128">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1347f-129">通常、`Is` または `IsNot` 演算子では、比較を実行するためにプロパティの値を読み取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="1347f-129">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="1347f-130">ただし、プロパティに現在 `Nothing` が格納されている場合は、プロパティによって Web サービスの新しいインスタンスが作成され、そのインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="1347f-130">However, if the property currently stores `Nothing`, the property creates a new instance of the Web service and then returns that instance.</span></span> <span data-ttu-id="1347f-131">ただし、Visual Basic コンパイラでは、`My.WebServices` オブジェクトのプロパティが特別に処理されるため、`Is` または `IsNot` 演算子によって、値を変更せずにプロパティの状態をチェックできます。</span><span class="sxs-lookup"><span data-stu-id="1347f-131">However, the Visual Basic compiler treats the properties of the `My.WebServices` object specially, and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1347f-132">例</span><span class="sxs-lookup"><span data-stu-id="1347f-132">Example</span></span>  

 <span data-ttu-id="1347f-133">この例では、`TemperatureConverter` XML Web サービスの `FahrenheitToCelsius` メソッドを呼び出して、その結果を返しています。</span><span class="sxs-lookup"><span data-stu-id="1347f-133">This example calls the `FahrenheitToCelsius` method of the `TemperatureConverter` XML Web service, and returns the result.</span></span>  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 <span data-ttu-id="1347f-134">この例を機能させるには、プロジェクトで `Converter` という名前の Web サービスを参照し、その Web サービスで `ConvertTemperature` メソッドを公開している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1347f-134">For this example to work, your project must reference a Web service named `Converter`, and that Web service must expose the `ConvertTemperature` method.</span></span> <span data-ttu-id="1347f-135">詳細については、「[アプリケーションの Web サービスへのアクセス](../../developing-apps/programming/accessing-application-web-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1347f-135">For more information, see [Accessing Application Web Services](../../developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="1347f-136">このコードは、Web アプリケーション プロジェクトでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="1347f-136">This code does not work in a Web application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1347f-137">必要条件</span><span class="sxs-lookup"><span data-stu-id="1347f-137">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="1347f-138">プロジェクトの種類別の可用性</span><span class="sxs-lookup"><span data-stu-id="1347f-138">Availability by Project Type</span></span>  
  
|<span data-ttu-id="1347f-139">プロジェクトの種類</span><span class="sxs-lookup"><span data-stu-id="1347f-139">Project type</span></span>|<span data-ttu-id="1347f-140">使用可能</span><span class="sxs-lookup"><span data-stu-id="1347f-140">Available</span></span>|  
|---|---|  
|<span data-ttu-id="1347f-141">Windows アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1347f-141">Windows Application</span></span>|<span data-ttu-id="1347f-142">**はい**</span><span class="sxs-lookup"><span data-stu-id="1347f-142">**Yes**</span></span>|  
|<span data-ttu-id="1347f-143">クラス ライブラリ</span><span class="sxs-lookup"><span data-stu-id="1347f-143">Class Library</span></span>|<span data-ttu-id="1347f-144">**はい**</span><span class="sxs-lookup"><span data-stu-id="1347f-144">**Yes**</span></span>|  
|<span data-ttu-id="1347f-145">コンソール アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1347f-145">Console Application</span></span>|<span data-ttu-id="1347f-146">**はい**</span><span class="sxs-lookup"><span data-stu-id="1347f-146">**Yes**</span></span>|  
|<span data-ttu-id="1347f-147">Windows コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="1347f-147">Windows Control Library</span></span>|<span data-ttu-id="1347f-148">**はい**</span><span class="sxs-lookup"><span data-stu-id="1347f-148">**Yes**</span></span>|  
|<span data-ttu-id="1347f-149">Web コントロール ライブラリ</span><span class="sxs-lookup"><span data-stu-id="1347f-149">Web Control Library</span></span>|<span data-ttu-id="1347f-150">**はい**</span><span class="sxs-lookup"><span data-stu-id="1347f-150">**Yes**</span></span>|  
|<span data-ttu-id="1347f-151">Windows サービス</span><span class="sxs-lookup"><span data-stu-id="1347f-151">Windows Service</span></span>|<span data-ttu-id="1347f-152">**はい**</span><span class="sxs-lookup"><span data-stu-id="1347f-152">**Yes**</span></span>|  
|<span data-ttu-id="1347f-153">Web サイト</span><span class="sxs-lookup"><span data-stu-id="1347f-153">Web Site</span></span>|<span data-ttu-id="1347f-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="1347f-154">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1347f-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="1347f-155">See also</span></span>

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [<span data-ttu-id="1347f-156">アプリケーションの Web サービスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="1347f-156">Accessing Application Web Services</span></span>](../../developing-apps/programming/accessing-application-web-services.md)
