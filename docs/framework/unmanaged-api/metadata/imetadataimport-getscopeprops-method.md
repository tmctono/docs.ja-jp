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
ms.openlocfilehash: 0916b6382bb9352616d85e21f423301dc6aa9fa9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490849"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="f7df0-102">IMetaDataImport::GetScopeProps メソッド</span><span class="sxs-lookup"><span data-stu-id="f7df0-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="f7df0-103">現在のメタデータ スコープにあるアセンブリまたはモジュールの名前、およびオプションでバージョン ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="f7df0-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7df0-104">構文</span><span class="sxs-lookup"><span data-stu-id="f7df0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7df0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7df0-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="f7df0-106">入出力アセンブリ名またはモジュール名のバッファー。</span><span class="sxs-lookup"><span data-stu-id="f7df0-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="f7df0-107">からのワイド文字のサイズ `szName` 。</span><span class="sxs-lookup"><span data-stu-id="f7df0-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="f7df0-108">入出力で返されたワイド文字の数 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="f7df0-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="f7df0-109">[out、省略可能]アセンブリまたはモジュールのバージョンを一意に識別する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f7df0-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7df0-110">解説</span><span class="sxs-lookup"><span data-stu-id="f7df0-110">Remarks</span></span>  
 <span data-ttu-id="f7df0-111">これらのプロパティを設定するには、 [IMetaDataEmit:: SetModuleProps](imetadataemit-setmoduleprops-method.md)メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7df0-111">The [IMetaDataEmit::SetModuleProps](imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7df0-112">要件</span><span class="sxs-lookup"><span data-stu-id="f7df0-112">Requirements</span></span>  
 <span data-ttu-id="f7df0-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7df0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7df0-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="f7df0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7df0-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f7df0-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f7df0-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7df0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7df0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7df0-117">See also</span></span>

- [<span data-ttu-id="f7df0-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7df0-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f7df0-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7df0-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
