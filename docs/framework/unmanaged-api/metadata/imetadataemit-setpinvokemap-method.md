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
ms.openlocfilehash: 4e2a78e2d049e952aa1be0b3a8fd640eb18d0320
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440570"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="87c2f-102">IMetaDataEmit::SetPinvokeMap メソッド</span><span class="sxs-lookup"><span data-stu-id="87c2f-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="87c2f-103">[IMetaDataEmit::D efinepinvokemap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)の前の呼び出しで定義されているように、メソッドの PInvoke 署名の機能を設定または変更します。</span><span class="sxs-lookup"><span data-stu-id="87c2f-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87c2f-104">構文</span><span class="sxs-lookup"><span data-stu-id="87c2f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87c2f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87c2f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="87c2f-106">からマッピング情報が適用される `mdToken`。</span><span class="sxs-lookup"><span data-stu-id="87c2f-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="87c2f-107">からマッピングを行うために PInvoke によって使用されるフラグ。</span><span class="sxs-lookup"><span data-stu-id="87c2f-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="87c2f-108">これは `CorPinvokeMap` 値のビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="87c2f-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="87c2f-109">からネイティブ DLL 内のターゲットエクスポートの名前。</span><span class="sxs-lookup"><span data-stu-id="87c2f-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="87c2f-110">からターゲットのアンマネージ DLL の `mdModuleRef` トークン。</span><span class="sxs-lookup"><span data-stu-id="87c2f-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87c2f-111">要件</span><span class="sxs-lookup"><span data-stu-id="87c2f-111">Requirements</span></span>  
 <span data-ttu-id="87c2f-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87c2f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87c2f-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="87c2f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="87c2f-114">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="87c2f-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87c2f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87c2f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c2f-116">参照</span><span class="sxs-lookup"><span data-stu-id="87c2f-116">See also</span></span>

- [<span data-ttu-id="87c2f-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87c2f-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="87c2f-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87c2f-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
