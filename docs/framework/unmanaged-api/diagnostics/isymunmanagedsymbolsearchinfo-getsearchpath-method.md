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
ms.openlocfilehash: 62eb5782071b42df1a035a4553b6cf9da53e24ac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778100"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="96853-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath メソッド</span><span class="sxs-lookup"><span data-stu-id="96853-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="96853-103">検索パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="96853-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96853-104">構文</span><span class="sxs-lookup"><span data-stu-id="96853-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96853-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96853-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="96853-106">[out]ポインター、`ULONG32`検索パスの格納に必要なバッファーの文字のサイズを受け取る。</span><span class="sxs-lookup"><span data-stu-id="96853-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96853-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="96853-107">Return Value</span></span>  
 <span data-ttu-id="96853-108">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="96853-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96853-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="96853-109">Requirements</span></span>  
 <span data-ttu-id="96853-110">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="96853-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96853-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="96853-111">See also</span></span>

- [<span data-ttu-id="96853-112">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96853-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
