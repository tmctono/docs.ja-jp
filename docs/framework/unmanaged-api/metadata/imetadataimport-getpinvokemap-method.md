---
title: IMetaDataImport::GetPinvokeMap メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 99aea385cf5e3c8bcf7cf39b7cc5618f99f8a631
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121707"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="401eb-102">IMetaDataImport::GetPinvokeMap メソッド</span><span class="sxs-lookup"><span data-stu-id="401eb-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="401eb-103">PInvoke 呼び出しの対象アセンブリを表す ModuleRef トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="401eb-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="401eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="401eb-104">Syntax</span></span>  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="401eb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="401eb-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="401eb-106">[in]PInvoke マッピング メタデータを取得する FieldDef または MethodDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="401eb-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="401eb-107">[out]フラグを使用してマップへのポインター。</span><span class="sxs-lookup"><span data-stu-id="401eb-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="401eb-108">この値はビットマスクから、 [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="401eb-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="401eb-109">[out]DLL の非管理対象のターゲットの名前。</span><span class="sxs-lookup"><span data-stu-id="401eb-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="401eb-110">[in]ワイド文字単位サイズ`szImportName`します。</span><span class="sxs-lookup"><span data-stu-id="401eb-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="401eb-111">[out]返されるワイド文字数`szImportName`します。</span><span class="sxs-lookup"><span data-stu-id="401eb-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="401eb-112">[out]非管理対象のターゲットのオブジェクト ライブラリを表す ModuleRef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="401eb-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="401eb-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="401eb-113">Requirements</span></span>  
 <span data-ttu-id="401eb-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="401eb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="401eb-115">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="401eb-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="401eb-116">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="401eb-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="401eb-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="401eb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401eb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="401eb-118">See also</span></span>

- [<span data-ttu-id="401eb-119">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="401eb-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="401eb-120">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="401eb-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
