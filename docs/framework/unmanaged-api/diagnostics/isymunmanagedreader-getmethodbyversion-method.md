---
title: ISymUnmanagedReader::GetMethodByVersion メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3210f0186401729a5bc95369e88b290ae49a634
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776994"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="bd0a9-102">ISymUnmanagedReader::GetMethodByVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="bd0a9-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="bd0a9-103">メソッドのトークンと編集、コピーのバージョン番号を指定のシンボル リーダー メソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="bd0a9-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="bd0a9-104">バージョン番号は、1 から開始し、メソッドは、編集、コピー操作の結果として変更されるたびにインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="bd0a9-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd0a9-105">構文</span><span class="sxs-lookup"><span data-stu-id="bd0a9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd0a9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd0a9-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="bd0a9-107">[in]メソッド トークンです。</span><span class="sxs-lookup"><span data-stu-id="bd0a9-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="bd0a9-108">[in]メソッドのバージョン。</span><span class="sxs-lookup"><span data-stu-id="bd0a9-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="bd0a9-109">[out]返されたインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bd0a9-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd0a9-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="bd0a9-110">Return Value</span></span>  
 <span data-ttu-id="bd0a9-111">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="bd0a9-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd0a9-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="bd0a9-112">Requirements</span></span>  
 <span data-ttu-id="bd0a9-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bd0a9-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd0a9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd0a9-114">See also</span></span>

- [<span data-ttu-id="bd0a9-115">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd0a9-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
