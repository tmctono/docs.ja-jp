---
title: ISymENCUnmanagedMethod::GetSourceExtentInDocument メソッド
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
ms.openlocfilehash: 3ac8bb3a20ce82b734a572832a9cbb75fa2568c4
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441904"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="356bd-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument メソッド</span><span class="sxs-lookup"><span data-stu-id="356bd-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="356bd-103">特定のドキュメント内のメソッドの最小の開始行と最大の終了行を取得します。</span><span class="sxs-lookup"><span data-stu-id="356bd-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="356bd-104">構文</span><span class="sxs-lookup"><span data-stu-id="356bd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="356bd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="356bd-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="356bd-106">からドキュメントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="356bd-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="356bd-107">入出力開始行を受け取るへのポインター `ULONG32` 。</span><span class="sxs-lookup"><span data-stu-id="356bd-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="356bd-108">入出力終了行を受け取るへのポインター `ULONG32` 。</span><span class="sxs-lookup"><span data-stu-id="356bd-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="356bd-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="356bd-109">Return Value</span></span>  
 <span data-ttu-id="356bd-110">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="356bd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="356bd-111">要件</span><span class="sxs-lookup"><span data-stu-id="356bd-111">Requirements</span></span>  
 <span data-ttu-id="356bd-112">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="356bd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="356bd-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="356bd-113">See also</span></span>

- [<span data-ttu-id="356bd-114">ISymENCUnmanagedMethod インターフェイス</span><span class="sxs-lookup"><span data-stu-id="356bd-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
