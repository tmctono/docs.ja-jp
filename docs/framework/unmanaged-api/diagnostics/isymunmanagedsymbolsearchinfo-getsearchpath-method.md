---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPath メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 649f44bd7966b9ca89d2d040b7eede662404aa0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638607"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="902f1-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath メソッド</span><span class="sxs-lookup"><span data-stu-id="902f1-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="902f1-103">検索パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="902f1-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="902f1-104">構文</span><span class="sxs-lookup"><span data-stu-id="902f1-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="902f1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="902f1-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="902f1-106">[out]ポインター、`ULONG32`検索パスの格納に必要なバッファーの文字のサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="902f1-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="902f1-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="902f1-107">Return Value</span></span>  
 <span data-ttu-id="902f1-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="902f1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="902f1-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="902f1-109">Requirements</span></span>  
 <span data-ttu-id="902f1-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="902f1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="902f1-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="902f1-111">See also</span></span>

- [<span data-ttu-id="902f1-112">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="902f1-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
