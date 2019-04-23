---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 7e6a96c217b038e870b4e865315766afa3b3c757
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975353"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="2fbce-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="2fbce-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="2fbce-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="2fbce-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fbce-104">構文</span><span class="sxs-lookup"><span data-stu-id="2fbce-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2fbce-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2fbce-105">Methods</span></span>  
 <span data-ttu-id="2fbce-106">MustUnderstandBehavior クラスで定義されるメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="2fbce-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2fbce-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2fbce-107">Properties</span></span>  
 <span data-ttu-id="2fbce-108">MustUnderstandBehavior クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="2fbce-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="2fbce-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="2fbce-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="2fbce-110">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="2fbce-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="2fbce-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2fbce-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2fbce-112">`true` の場合、未処理の `MustUnderstand` 属性を持つすべての SOAP ヘッダーは、動作が例外をスローする原因となります。</span><span class="sxs-lookup"><span data-stu-id="2fbce-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fbce-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="2fbce-113">Requirements</span></span>  
  
|<span data-ttu-id="2fbce-114">MOF</span><span class="sxs-lookup"><span data-stu-id="2fbce-114">MOF</span></span>|<span data-ttu-id="2fbce-115">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="2fbce-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2fbce-116">名前空間</span><span class="sxs-lookup"><span data-stu-id="2fbce-116">Namespace</span></span>|<span data-ttu-id="2fbce-117">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="2fbce-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2fbce-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fbce-118">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
