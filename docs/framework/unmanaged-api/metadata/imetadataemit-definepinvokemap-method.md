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
ms.openlocfilehash: e414bc5a7d537e8d153541f05b22dd91578e8739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177750"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="82973-102">IMetaDataEmit::DefinePinvokeMap メソッド</span><span class="sxs-lookup"><span data-stu-id="82973-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="82973-103">指定したトークンによって参照されるメソッドの PInvoke シグネチャの機能を設定します。</span><span class="sxs-lookup"><span data-stu-id="82973-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82973-104">構文</span><span class="sxs-lookup"><span data-stu-id="82973-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82973-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82973-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="82973-106">[in]ターゲット メソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="82973-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="82973-107">[in]PInvoke がマッピングを実行するために使用するフラグ。</span><span class="sxs-lookup"><span data-stu-id="82973-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="82973-108">[in]アンマネージ DLL 内のターゲット エクスポート メソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="82973-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="82973-109">[in]ターゲットネイティブ DLL のトークン。</span><span class="sxs-lookup"><span data-stu-id="82973-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82973-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="82973-110">Requirements</span></span>  
 <span data-ttu-id="82973-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82973-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82973-112">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="82973-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82973-113">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="82973-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82973-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82973-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82973-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="82973-115">See also</span></span>

- [<span data-ttu-id="82973-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82973-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="82973-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="82973-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
