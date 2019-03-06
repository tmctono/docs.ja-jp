---
title: ISymENCUnmanagedMethod::GetFileNameFromOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: df1e9d317294127a931bebf100295290a0dd6b23
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471837"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="d38aa-102">ISymENCUnmanagedMethod::GetFileNameFromOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="d38aa-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="d38aa-103">オフセットに関連付けられている行のファイル名を取得します。</span><span class="sxs-lookup"><span data-stu-id="d38aa-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d38aa-104">構文</span><span class="sxs-lookup"><span data-stu-id="d38aa-104">Syntax</span></span>  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d38aa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d38aa-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="d38aa-106">[in]A`ULONG32`オフセットを格納しています。</span><span class="sxs-lookup"><span data-stu-id="d38aa-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d38aa-107">[in]A`ULONG32`のサイズを示す、`szName`バッファー。</span><span class="sxs-lookup"><span data-stu-id="d38aa-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d38aa-108">[out]ポインターを`ULONG32`ファイル名を格納するために必要なバッファーの文字のサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="d38aa-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="d38aa-109">[out]ファイル名を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="d38aa-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d38aa-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="d38aa-110">Return Value</span></span>  
 <span data-ttu-id="d38aa-111">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="d38aa-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d38aa-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d38aa-112">Requirements</span></span>  
 <span data-ttu-id="d38aa-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d38aa-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d38aa-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d38aa-114">See also</span></span>
- [<span data-ttu-id="d38aa-115">ISymENCUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d38aa-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
