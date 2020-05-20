---
title: ISymUnmanagedDocument::HasEmbeddedSource メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
ms.openlocfilehash: d654f6d57bd784063fc7f87dd9767bdc27ad2776
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615580"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="01d30-102">ISymUnmanagedDocument::HasEmbeddedSource メソッド</span><span class="sxs-lookup"><span data-stu-id="01d30-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="01d30-103">`true`ドキュメントがデバッグシンボルに埋め込まれている場合はを返します。それ以外の場合はを返し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="01d30-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01d30-104">構文</span><span class="sxs-lookup"><span data-stu-id="01d30-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01d30-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="01d30-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="01d30-106">入出力ドキュメントにデバッグシンボルに埋め込まれたソースがあるかどうかを示す変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="01d30-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01d30-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="01d30-107">Return Value</span></span>  
 <span data-ttu-id="01d30-108">メソッドが成功した場合は S_OK します。</span><span class="sxs-lookup"><span data-stu-id="01d30-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01d30-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="01d30-109">See also</span></span>

- [<span data-ttu-id="01d30-110">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01d30-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
