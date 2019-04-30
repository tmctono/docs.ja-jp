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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bcd200b7fa431f193dd202c3c2a690aa22ec8e32
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986259"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="eef75-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap メソッド</span><span class="sxs-lookup"><span data-stu-id="eef75-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="eef75-103">指定したメソッドのトークンと、エディット コンティニュ バージョン番号のシンボル リーダー メソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="eef75-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="eef75-104">バージョン番号は 1 から開始し、エディット コンティニュ操作の結果として、メソッドが変更されるたびにインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="eef75-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eef75-105">構文</span><span class="sxs-lookup"><span data-stu-id="eef75-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eef75-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eef75-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="eef75-107">[in]メソッドのメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="eef75-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="eef75-108">[in]メソッドのバージョン。</span><span class="sxs-lookup"><span data-stu-id="eef75-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="eef75-109">[out]返されたポインター [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="eef75-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eef75-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="eef75-110">Return Value</span></span>  
 <span data-ttu-id="eef75-111">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="eef75-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eef75-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="eef75-112">Requirements</span></span>  
 <span data-ttu-id="eef75-113">**ヘッダー:** CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="eef75-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="eef75-114">CorSym.h</span><span class="sxs-lookup"><span data-stu-id="eef75-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef75-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="eef75-115">See also</span></span>

- [<span data-ttu-id="eef75-116">ISymUnmanagedReader2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eef75-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
