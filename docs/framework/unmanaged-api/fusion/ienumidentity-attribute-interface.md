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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbb3ac150ebfe9fe3698427d8bb2bfb3e3347c07
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796456"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="46175-102">IEnumIDENTITY_ATTRIBUTE インターフェイス</span><span class="sxs-lookup"><span data-stu-id="46175-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="46175-103">現在のスコープ内のコードオブジェクトの属性の列挙子として機能します。</span><span class="sxs-lookup"><span data-stu-id="46175-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="46175-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="46175-104">Methods</span></span>  
  
|<span data-ttu-id="46175-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="46175-105">Method</span></span>|<span data-ttu-id="46175-106">説明</span><span class="sxs-lookup"><span data-stu-id="46175-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="46175-107">`IEnumIDENTITY_ATTRIBUTE` この`IEnumIDENTITY_ATTRIBUTE`と同じメンバーを含む新しいへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="46175-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="46175-108">この`IEnumIDENTITY_ATTRIBUTE`の要素に格納されているデータを、指定したデータバッファーに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="46175-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="46175-109">指定した数の属性を、現在の位置から開始して取得します。</span><span class="sxs-lookup"><span data-stu-id="46175-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="46175-110">命令ポインターをこの`IEnumIDENTITY_ATTRIBUTE`の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="46175-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="46175-111">現在位置を開始位置として、指定した要素数だけ前方に命令ポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="46175-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="46175-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="46175-112">Requirements</span></span>  
 <span data-ttu-id="46175-113">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="46175-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46175-114">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="46175-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="46175-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46175-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46175-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="46175-116">See also</span></span>

- [<span data-ttu-id="46175-117">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="46175-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
