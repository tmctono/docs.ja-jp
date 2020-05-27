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
ms.openlocfilehash: 91ef9eaa855ed841bc75bfaeead462f045eb1d8b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007456"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="d9fc1-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="d9fc1-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="d9fc1-103">このメソッドは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="d9fc1-103">This method is not implemented.</span></span> <span data-ttu-id="d9fc1-104">呼び出された場合は E_NOTIMPL を返します。</span><span class="sxs-lookup"><span data-stu-id="d9fc1-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9fc1-105">構文</span><span class="sxs-lookup"><span data-stu-id="d9fc1-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9fc1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d9fc1-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="d9fc1-107">からスコープを開く対象の型情報を提供する[ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9fc1-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="d9fc1-108">からOpen モードフラグ。</span><span class="sxs-lookup"><span data-stu-id="d9fc1-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="d9fc1-109">から目的のインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d9fc1-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="d9fc1-110">入出力返されたインターフェイスへのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9fc1-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9fc1-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="d9fc1-111">Requirements</span></span>  
 <span data-ttu-id="d9fc1-112">**プラットフォーム:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9fc1-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9fc1-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="d9fc1-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9fc1-114">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9fc1-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9fc1-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9fc1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9fc1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9fc1-116">See also</span></span>

- [<span data-ttu-id="d9fc1-117">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9fc1-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="d9fc1-118">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9fc1-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
