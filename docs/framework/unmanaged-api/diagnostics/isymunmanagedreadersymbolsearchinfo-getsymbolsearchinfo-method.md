---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d910f9e93dbd90f9e23c5f32903a8d819ea01f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751473"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="67907-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="67907-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="67907-103">シンボルの検索情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="67907-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67907-104">構文</span><span class="sxs-lookup"><span data-stu-id="67907-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67907-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="67907-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="67907-106">[in]A`ULONG32`のサイズを示す`rgpSearchInfo`します。</span><span class="sxs-lookup"><span data-stu-id="67907-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="67907-107">[out]ポインター、`ULONG32`検索情報の格納に必要なバッファーのサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="67907-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="67907-108">[out]設定されているポインターに返された[ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="67907-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67907-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="67907-109">Return Value</span></span>  
 <span data-ttu-id="67907-110">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="67907-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67907-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="67907-111">Requirements</span></span>  
 <span data-ttu-id="67907-112">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="67907-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67907-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="67907-113">See also</span></span>

- [<span data-ttu-id="67907-114">ISymUnmanagedReaderSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67907-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
