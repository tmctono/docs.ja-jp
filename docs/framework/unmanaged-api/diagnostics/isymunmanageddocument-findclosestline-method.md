---
title: ISymUnmanagedDocument::FindClosestLine メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
ms.openlocfilehash: 9e6134d39096c4ab157aa545646d83339f92a0b8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441033"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="0e480-102">ISymUnmanagedDocument::FindClosestLine メソッド</span><span class="sxs-lookup"><span data-stu-id="0e480-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="0e480-103">このドキュメント内の行が指定されている場合は、シーケンスポイントで最も近い行を返します。</span><span class="sxs-lookup"><span data-stu-id="0e480-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e480-104">構文</span><span class="sxs-lookup"><span data-stu-id="0e480-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e480-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0e480-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="0e480-106">からこのドキュメント内の行。</span><span class="sxs-lookup"><span data-stu-id="0e480-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0e480-107">入出力行を受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0e480-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e480-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="0e480-108">Return Value</span></span>  
 <span data-ttu-id="0e480-109">メソッドが成功した場合は S_OK。それ以外の場合は、エラーコード。</span><span class="sxs-lookup"><span data-stu-id="0e480-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e480-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e480-110">See also</span></span>

- [<span data-ttu-id="0e480-111">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e480-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
