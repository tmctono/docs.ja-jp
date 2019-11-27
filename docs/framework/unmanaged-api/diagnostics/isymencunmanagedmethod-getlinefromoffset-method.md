---
title: ISymENCUnmanagedMethod::GetLineFromOffset メソッド
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
ms.openlocfilehash: 94a571a4bc01b805387aebe5a6e23bad0b735313
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448639"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="1593a-102">ISymENCUnmanagedMethod::GetLineFromOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="1593a-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>
<span data-ttu-id="1593a-103">オフセットに関連付けられている行情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="1593a-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="1593a-104">オフセットパラメーター (`dwOffset`) がシーケンスポイントでない場合、このメソッドは、前のオフセットに関連付けられている行情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="1593a-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1593a-105">構文</span><span class="sxs-lookup"><span data-stu-id="1593a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1593a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1593a-106">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="1593a-107">からオフセットを格納している `ULONG32`。</span><span class="sxs-lookup"><span data-stu-id="1593a-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="1593a-108">入出力行を受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1593a-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="1593a-109">入出力列を受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1593a-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="1593a-110">入出力終了行を受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1593a-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="1593a-111">入出力終了列を受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1593a-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="1593a-112">入出力関連付けられたシーケンスポイントを受け取る `ULONG32` へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1593a-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1593a-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="1593a-113">Return Value</span></span>  
 <span data-ttu-id="1593a-114">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="1593a-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1593a-115">要件</span><span class="sxs-lookup"><span data-stu-id="1593a-115">Requirements</span></span>  
 <span data-ttu-id="1593a-116">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="1593a-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1593a-117">参照</span><span class="sxs-lookup"><span data-stu-id="1593a-117">See also</span></span>

- [<span data-ttu-id="1593a-118">ISymENCUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1593a-118">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
