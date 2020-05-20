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
ms.openlocfilehash: d9431a533a32fd15931072cfbabd10bbc0e6d4ad
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610679"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="4dadd-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath メソッド</span><span class="sxs-lookup"><span data-stu-id="4dadd-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="4dadd-103">検索パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="4dadd-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dadd-104">構文</span><span class="sxs-lookup"><span data-stu-id="4dadd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dadd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4dadd-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="4dadd-106">入出力`ULONG32`検索パスを格納するために必要なバッファーのサイズ (文字数) を受け取るへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4dadd-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dadd-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="4dadd-107">Return Value</span></span>  
 <span data-ttu-id="4dadd-108">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="4dadd-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dadd-109">要件</span><span class="sxs-lookup"><span data-stu-id="4dadd-109">Requirements</span></span>  
 <span data-ttu-id="4dadd-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="4dadd-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dadd-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="4dadd-111">See also</span></span>

- [<span data-ttu-id="4dadd-112">ISymUnmanagedSymbolSearchInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4dadd-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
