---
title: ISymUnmanagedDocument::GetLanguageVendor メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
ms.openlocfilehash: e0a4c190f0f8e91886563477500c0e57e3516dfa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614566"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="52e39-102">ISymUnmanagedDocument::GetLanguageVendor メソッド</span><span class="sxs-lookup"><span data-stu-id="52e39-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="52e39-103">このドキュメントの言語販売元を取得します。</span><span class="sxs-lookup"><span data-stu-id="52e39-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52e39-104">構文</span><span class="sxs-lookup"><span data-stu-id="52e39-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52e39-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="52e39-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="52e39-106">入出力言語ベンダーを受け取る変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="52e39-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52e39-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="52e39-107">Return Value</span></span>  
 <span data-ttu-id="52e39-108">メソッドが成功した場合は S_OK します。</span><span class="sxs-lookup"><span data-stu-id="52e39-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e39-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="52e39-109">See also</span></span>

- [<span data-ttu-id="52e39-110">ISymUnmanagedDocument インターフェイス</span><span class="sxs-lookup"><span data-stu-id="52e39-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
