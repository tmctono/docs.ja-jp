---
title: IMetaDataEmit::DefinePinvokeMap メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6421ca47c3439d94c1ae86caaf2198298872d53
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777523"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="73186-102">IMetaDataEmit::DefinePinvokeMap メソッド</span><span class="sxs-lookup"><span data-stu-id="73186-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="73186-103">指定したトークンによって参照されるメソッドの PInvoke 署名の機能を設定します。</span><span class="sxs-lookup"><span data-stu-id="73186-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73186-104">構文</span><span class="sxs-lookup"><span data-stu-id="73186-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73186-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73186-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="73186-106">[in]ターゲット メソッドのトークンです。</span><span class="sxs-lookup"><span data-stu-id="73186-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="73186-107">[in]PInvoke によって、マッピングを行うために使用するフラグ。</span><span class="sxs-lookup"><span data-stu-id="73186-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="73186-108">[in]ターゲットの名前は、アンマネージ DLL 内のメソッドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="73186-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="73186-109">[in]ターゲットのトークン ネイティブ DLL。</span><span class="sxs-lookup"><span data-stu-id="73186-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73186-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="73186-110">Requirements</span></span>  
 <span data-ttu-id="73186-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73186-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73186-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="73186-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73186-113">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="73186-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73186-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73186-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73186-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="73186-115">See also</span></span>

- [<span data-ttu-id="73186-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73186-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="73186-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="73186-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
