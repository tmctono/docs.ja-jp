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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bbd8476b7778de6d0023f3a8522a44be6626884
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751520"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="ae550-102">IEnumDefinitionIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae550-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="ae550-103">コレクションの列挙子として機能`IDefinitionIdentity`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ae550-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae550-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae550-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="ae550-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ae550-105">Methods</span></span>  
  
|<span data-ttu-id="ae550-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="ae550-106">Method</span></span>|<span data-ttu-id="ae550-107">説明</span><span class="sxs-lookup"><span data-stu-id="ae550-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="ae550-108">新しいインターフェイス ポインターを取得`IEnumDefinitionIdentity`これと同じメンバーを含むオブジェクト`IEnumDefinitionIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="ae550-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="ae550-109">指定した数を取得`IDefinitionIdentity`オブジェクト、現在の位置で開始します。</span><span class="sxs-lookup"><span data-stu-id="ae550-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="ae550-110">これの先頭に、命令ポインターを移動`IEnumDefinitionIdentity`します。</span><span class="sxs-lookup"><span data-stu-id="ae550-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="ae550-111">指定数の要素を現在の位置からでは、転送、命令ポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="ae550-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae550-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="ae550-112">Requirements</span></span>  
 <span data-ttu-id="ae550-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae550-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae550-114">**ヘッダー:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="ae550-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="ae550-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae550-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae550-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae550-116">See also</span></span>

- [<span data-ttu-id="ae550-117">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae550-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="ae550-118">IDefinitionIdentity インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae550-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
