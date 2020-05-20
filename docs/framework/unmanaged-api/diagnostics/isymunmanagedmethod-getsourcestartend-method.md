---
title: ISymUnmanagedMethod::GetSourceStartEnd メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
ms.openlocfilehash: 25e797fdf563a01ab727f16e7173eec2552eeb27
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614423"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="bac5e-102">ISymUnmanagedMethod::GetSourceStartEnd メソッド</span><span class="sxs-lookup"><span data-stu-id="bac5e-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="bac5e-103">このメソッドのソースのドキュメントの開始位置と終了位置を取得します。</span><span class="sxs-lookup"><span data-stu-id="bac5e-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="bac5e-104">最初の配列の位置は start で、2番目の配列の位置は末尾です。</span><span class="sxs-lookup"><span data-stu-id="bac5e-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bac5e-105">構文</span><span class="sxs-lookup"><span data-stu-id="bac5e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bac5e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bac5e-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="bac5e-107">から開始と終了のソースドキュメント。</span><span class="sxs-lookup"><span data-stu-id="bac5e-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="bac5e-108">から対応するソースドキュメントの開始行と終了行。</span><span class="sxs-lookup"><span data-stu-id="bac5e-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="bac5e-109">から対応するソースドキュメント内の開始列と終了列。</span><span class="sxs-lookup"><span data-stu-id="bac5e-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="bac5e-110">[出力] `true`位置が定義されている場合は。それ以外の場合は `false` 。</span><span class="sxs-lookup"><span data-stu-id="bac5e-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bac5e-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="bac5e-111">Return Value</span></span>  
 <span data-ttu-id="bac5e-112">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="bac5e-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bac5e-113">要件</span><span class="sxs-lookup"><span data-stu-id="bac5e-113">Requirements</span></span>  
 <span data-ttu-id="bac5e-114">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="bac5e-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac5e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bac5e-115">See also</span></span>

- [<span data-ttu-id="bac5e-116">ISymUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bac5e-116">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
