---
title: IMetaDataEmit::SetPinvokeMap メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: 4c68754bc44fe035fd8e7143c52895928beae395
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175591"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="bd0aa-102">IMetaDataEmit::SetPinvokeMap メソッド</span><span class="sxs-lookup"><span data-stu-id="bd0aa-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="bd0aa-103">[:D メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)の PInvoke シグネチャの機能を設定または変更します。</span><span class="sxs-lookup"><span data-stu-id="bd0aa-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd0aa-104">構文</span><span class="sxs-lookup"><span data-stu-id="bd0aa-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd0aa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd0aa-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="bd0aa-106">[in]マッピング`mdToken`情報が適用される先。</span><span class="sxs-lookup"><span data-stu-id="bd0aa-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="bd0aa-107">[in]PInvoke がマッピングを実行するために使用するフラグ。</span><span class="sxs-lookup"><span data-stu-id="bd0aa-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="bd0aa-108">これは値の`CorPinvokeMap`ビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="bd0aa-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="bd0aa-109">[in]ネイティブ DLL 内のターゲット エクスポートの名前。</span><span class="sxs-lookup"><span data-stu-id="bd0aa-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="bd0aa-110">[in]ターゲット`mdModuleRef`アンマネージ DLL のトークン。</span><span class="sxs-lookup"><span data-stu-id="bd0aa-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd0aa-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="bd0aa-111">Requirements</span></span>  
 <span data-ttu-id="bd0aa-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd0aa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd0aa-113">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="bd0aa-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd0aa-114">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd0aa-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd0aa-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd0aa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd0aa-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd0aa-116">See also</span></span>

- [<span data-ttu-id="bd0aa-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd0aa-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bd0aa-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd0aa-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
