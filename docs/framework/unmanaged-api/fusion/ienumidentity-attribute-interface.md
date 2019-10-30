---
title: IEnumIDENTITY_ATTRIBUTE インターフェイス
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
ms.openlocfilehash: 7e6bc57fb470a5c12549bb5f9445ecf1551425a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107843"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="7665c-102">IEnumIDENTITY_ATTRIBUTE インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7665c-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="7665c-103">現在のスコープ内のコードオブジェクトの属性の列挙子として機能します。</span><span class="sxs-lookup"><span data-stu-id="7665c-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7665c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="7665c-104">Methods</span></span>  
  
|<span data-ttu-id="7665c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7665c-105">Method</span></span>|<span data-ttu-id="7665c-106">説明</span><span class="sxs-lookup"><span data-stu-id="7665c-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="7665c-107">この `IEnumIDENTITY_ATTRIBUTE`と同じメンバーを含む新しい `IEnumIDENTITY_ATTRIBUTE` へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="7665c-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="7665c-108">この `IEnumIDENTITY_ATTRIBUTE` の要素に格納されているデータを、指定したデータバッファーに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7665c-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="7665c-109">指定した数の属性を、現在の位置から開始して取得します。</span><span class="sxs-lookup"><span data-stu-id="7665c-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="7665c-110">命令ポインターをこの `IEnumIDENTITY_ATTRIBUTE`の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="7665c-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="7665c-111">現在位置を開始位置として、指定した要素数だけ前方に命令ポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="7665c-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7665c-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="7665c-112">Requirements</span></span>  
 <span data-ttu-id="7665c-113">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7665c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7665c-114">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="7665c-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="7665c-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7665c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7665c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7665c-116">See also</span></span>

- [<span data-ttu-id="7665c-117">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7665c-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
