---
title: IMetaDataEmit::SetFieldRVA メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
ms.openlocfilehash: d429995e41006798aee5f796150bedbd6ae87f6f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003872"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="8f923-102">IMetaDataEmit::SetFieldRVA メソッド</span><span class="sxs-lookup"><span data-stu-id="8f923-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="8f923-103">指定したトークンによって参照されるフィールドの相対仮想アドレスのグローバル変数値を設定します。</span><span class="sxs-lookup"><span data-stu-id="8f923-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f923-104">構文</span><span class="sxs-lookup"><span data-stu-id="8f923-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldRVA (
    [in]  mdFieldDef  fd,
    [in]  ULONG       ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f923-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f923-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="8f923-106">からターゲットフィールドのトークン。</span><span class="sxs-lookup"><span data-stu-id="8f923-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="8f923-107">からコードまたはデータ領域のアドレス。</span><span class="sxs-lookup"><span data-stu-id="8f923-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f923-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="8f923-108">Requirements</span></span>  
 <span data-ttu-id="8f923-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f923-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f923-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="8f923-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f923-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f923-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f923-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f923-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f923-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f923-113">See also</span></span>

- [<span data-ttu-id="8f923-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f923-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8f923-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f923-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
