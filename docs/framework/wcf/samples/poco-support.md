---
title: POCO サポート
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: 86ade3a6b045f6f7c57e4a95936b4f1574b51ff0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334901"
---
# <a name="poco-support"></a><span data-ttu-id="9141e-102">POCO サポート</span><span class="sxs-lookup"><span data-stu-id="9141e-102">POCO Support</span></span>
<span data-ttu-id="9141e-103">このサンプルでは、マークされていない型 (シリアル化属性が適用されていない型で、POCO (Plain Old CLR Object) 型と呼ばれる場合もあります) のシリアル化のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9141e-103">This sample demonstrates the serialization support for unmarked types; that is, types to which serialization attributes have not been applied, sometimes referred to as Plain Old CLR Object (POCO) types.</span></span> <span data-ttu-id="9141e-104"><xref:System.Runtime.Serialization.DataContractSerializer> では、既定のコンストラクタを持つすべてのマークされていないパブリック型について、データ コントラクトを推測します。</span><span class="sxs-lookup"><span data-stu-id="9141e-104">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract for all public unmarked types that have a default constructor.</span></span> <span data-ttu-id="9141e-105">データ コントラクトを使用すると、サービスと構造化データをやり取りできます。</span><span class="sxs-lookup"><span data-stu-id="9141e-105">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="9141e-106">マークされていない種類の詳細については、次を参照してください。[シリアル化できる型](../../../../docs/framework/wcf/feature-details/serializable-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="9141e-106">For more information about unmarked types, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
 <span data-ttu-id="9141e-107">このサンプルがに基づいて、 [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)がプリミティブ数値型ではなく複素数を使用します。</span><span class="sxs-lookup"><span data-stu-id="9141e-107">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), but uses complex numbers instead of primitive numeric types.</span></span> <span data-ttu-id="9141e-108">またに似ています、[基本的なデータ コントラクト](../../../../docs/framework/wcf/samples/basic-data-contract.md)点を除いて、サンプル、<xref:System.Runtime.Serialization.DataContractAttribute>と<xref:System.Runtime.Serialization.DataMemberAttribute>属性は使用されません。</span><span class="sxs-lookup"><span data-stu-id="9141e-108">It is also similar to the [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) sample, except that the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes are not used.</span></span>  
  
 <span data-ttu-id="9141e-109">サービスはインターネット インフォメーション サービス (IIS) によってホストされています。クライアントはコンソール アプリケーション (.exe) です。</span><span class="sxs-lookup"><span data-stu-id="9141e-109">The service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9141e-110">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9141e-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="9141e-111">`ComplexNumber` クラスは、`ServiceContract` で使用されます。</span><span class="sxs-lookup"><span data-stu-id="9141e-111">The `ComplexNumber` class is used in the `ServiceContract`.</span></span> <span data-ttu-id="9141e-112">次のサンプル コードに示すように、`ComplexNumber` 型には、<xref:System.Runtime.Serialization.DataContractAttribute> 属性と <xref:System.Runtime.Serialization.DataMemberAttribute> 属性がありません。</span><span class="sxs-lookup"><span data-stu-id="9141e-112">The `ComplexNumber` type does not have the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes, as shown in the following sample code.</span></span> <span data-ttu-id="9141e-113">既定では、パブリック プロパティとパブリック フィールドはすべてシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="9141e-113">By default, all public properties and fields are serialized.</span></span>  
  
```csharp
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9141e-114">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="9141e-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="9141e-115">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="9141e-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="9141e-116">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9141e-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="9141e-117">1 つまたは複数コンピュータ構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="9141e-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9141e-118">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="9141e-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9141e-119">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9141e-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9141e-120">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="9141e-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9141e-121">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="9141e-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a><span data-ttu-id="9141e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="9141e-122">See also</span></span>

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [<span data-ttu-id="9141e-123">シリアル化可能な型</span><span class="sxs-lookup"><span data-stu-id="9141e-123">Serializable Types</span></span>](../../../../docs/framework/wcf/feature-details/serializable-types.md)
