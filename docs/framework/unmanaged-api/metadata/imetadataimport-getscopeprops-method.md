---
title: IMetaDataImport::GetScopeProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: af1c3d599c5280e584ffb842c96c70a7c3d4ed08
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436877"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="0d3c2-102">IMetaDataImport::GetScopeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="0d3c2-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="0d3c2-103">現在のメタデータ スコープにあるアセンブリまたはモジュールの名前、およびオプションでバージョン ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="0d3c2-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d3c2-104">構文</span><span class="sxs-lookup"><span data-stu-id="0d3c2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d3c2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d3c2-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="0d3c2-106">入出力アセンブリ名またはモジュール名のバッファー。</span><span class="sxs-lookup"><span data-stu-id="0d3c2-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="0d3c2-107">から`szName`のワイド文字単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="0d3c2-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="0d3c2-108">入出力`szName`に返されるワイド文字数。</span><span class="sxs-lookup"><span data-stu-id="0d3c2-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="0d3c2-109">[out、省略可能]アセンブリまたはモジュールのバージョンを一意に識別する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0d3c2-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d3c2-110">コメント</span><span class="sxs-lookup"><span data-stu-id="0d3c2-110">Remarks</span></span>  
 <span data-ttu-id="0d3c2-111">これらのプロパティを設定するには、 [IMetaDataEmit:: SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0d3c2-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d3c2-112">要件</span><span class="sxs-lookup"><span data-stu-id="0d3c2-112">Requirements</span></span>  
 <span data-ttu-id="0d3c2-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d3c2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d3c2-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="0d3c2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d3c2-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0d3c2-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d3c2-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d3c2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d3c2-117">参照</span><span class="sxs-lookup"><span data-stu-id="0d3c2-117">See also</span></span>

- [<span data-ttu-id="0d3c2-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d3c2-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0d3c2-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d3c2-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
