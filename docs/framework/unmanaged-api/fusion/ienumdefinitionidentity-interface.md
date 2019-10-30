---
title: IEnumDefinitionIdentity インターフェイス
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
ms.openlocfilehash: 09c6431ec885c8b797dc9bb5f5c3ffe21890ccc7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107938"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="798ce-102">IEnumDefinitionIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="798ce-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="798ce-103">`IDefinitionIdentity` オブジェクトのコレクションの列挙子として機能します。</span><span class="sxs-lookup"><span data-stu-id="798ce-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="798ce-104">構文</span><span class="sxs-lookup"><span data-stu-id="798ce-104">Syntax</span></span>  
  
```cpp  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="798ce-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="798ce-105">Methods</span></span>  
  
|<span data-ttu-id="798ce-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="798ce-106">Method</span></span>|<span data-ttu-id="798ce-107">説明</span><span class="sxs-lookup"><span data-stu-id="798ce-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="798ce-108">この `IEnumDefinitionIdentity`と同じメンバーを含む新しい `IEnumDefinitionIdentity` オブジェクトへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="798ce-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="798ce-109">現在の位置から開始して、指定した数の `IDefinitionIdentity` オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="798ce-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="798ce-110">命令ポインターをこの `IEnumDefinitionIdentity`の先頭に移動します。</span><span class="sxs-lookup"><span data-stu-id="798ce-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="798ce-111">現在位置を開始位置として、指定した要素数だけ前方に命令ポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="798ce-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="798ce-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="798ce-112">Requirements</span></span>  
 <span data-ttu-id="798ce-113">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="798ce-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="798ce-114">**ヘッダー:** 分離 .h</span><span class="sxs-lookup"><span data-stu-id="798ce-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="798ce-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="798ce-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="798ce-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="798ce-116">See also</span></span>

- [<span data-ttu-id="798ce-117">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="798ce-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="798ce-118">IDefinitionIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="798ce-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
