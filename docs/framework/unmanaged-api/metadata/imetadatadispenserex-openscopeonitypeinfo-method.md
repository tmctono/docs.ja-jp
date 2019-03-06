---
title: IMetaDataDispenserEx::OpenScopeOnITypeInfo メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 122a31fab3bf7bf10eb2490a955fb8245ea0408b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471031"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="4c515-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="4c515-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="4c515-103">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="4c515-103">This method is not implemented.</span></span> <span data-ttu-id="4c515-104">呼び出された場合、E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="4c515-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c515-105">構文</span><span class="sxs-lookup"><span data-stu-id="4c515-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c515-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4c515-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="4c515-107">[in]ポインター、 [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo)を開くスコープ型情報を提供するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4c515-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="4c515-108">[in]Open モード フラグ。</span><span class="sxs-lookup"><span data-stu-id="4c515-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="4c515-109">[in]必要なインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4c515-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="4c515-110">[out]返されるインターフェイスへのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4c515-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c515-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="4c515-111">Requirements</span></span>  
 <span data-ttu-id="4c515-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c515-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c515-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4c515-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4c515-114">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="4c515-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4c515-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c515-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c515-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c515-116">See also</span></span>
- [<span data-ttu-id="4c515-117">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c515-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="4c515-118">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c515-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
