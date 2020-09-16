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
ms.openlocfilehash: 8e119093800ea0a0119ba25ba38cf2eaf9afe96b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540863"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="3314c-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="3314c-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="3314c-103">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="3314c-103">This method is not implemented.</span></span> <span data-ttu-id="3314c-104">呼び出された場合は E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="3314c-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3314c-105">構文</span><span class="sxs-lookup"><span data-stu-id="3314c-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3314c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3314c-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="3314c-107">からスコープを開く対象の型情報を提供する [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3314c-107">[in] Pointer to an [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="3314c-108">からOpen モードフラグ。</span><span class="sxs-lookup"><span data-stu-id="3314c-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="3314c-109">から目的のインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="3314c-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="3314c-110">入出力返されたインターフェイスへのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3314c-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3314c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3314c-111">Requirements</span></span>  
 <span data-ttu-id="3314c-112">**プラットフォーム:** 「 [システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3314c-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3314c-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="3314c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3314c-114">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="3314c-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3314c-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3314c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3314c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3314c-116">See also</span></span>

- [<span data-ttu-id="3314c-117">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3314c-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="3314c-118">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3314c-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
