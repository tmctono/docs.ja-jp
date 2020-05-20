---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
ms.openlocfilehash: b12ecfdaf7c90589ce2e96b39f7437444cb91b09
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615424"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="332aa-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap メソッド</span><span class="sxs-lookup"><span data-stu-id="332aa-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="332aa-103">メソッドトークンとエディットコンティニュバージョン番号を指定して、シンボルリーダーメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="332aa-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="332aa-104">バージョン番号は1から始まり、エディットコンティニュ操作の結果としてメソッドが変更されるたびに増分されます。</span><span class="sxs-lookup"><span data-stu-id="332aa-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="332aa-105">構文</span><span class="sxs-lookup"><span data-stu-id="332aa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="332aa-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="332aa-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="332aa-107">からメソッドメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="332aa-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="332aa-108">からメソッドのバージョン。</span><span class="sxs-lookup"><span data-stu-id="332aa-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="332aa-109">入出力返された[ISymUnmanagedMethod](isymunmanagedmethod-interface.md)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="332aa-109">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="332aa-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="332aa-110">Return Value</span></span>  
 <span data-ttu-id="332aa-111">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="332aa-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="332aa-112">要件</span><span class="sxs-lookup"><span data-stu-id="332aa-112">Requirements</span></span>  
 <span data-ttu-id="332aa-113">**ヘッダー:** CorSym .idl。</span><span class="sxs-lookup"><span data-stu-id="332aa-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="332aa-114">CorSym .h</span><span class="sxs-lookup"><span data-stu-id="332aa-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="332aa-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="332aa-115">See also</span></span>

- [<span data-ttu-id="332aa-116">ISymUnmanagedReader2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="332aa-116">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
