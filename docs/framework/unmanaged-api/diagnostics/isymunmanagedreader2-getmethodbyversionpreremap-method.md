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
ms.openlocfilehash: 2063856389b122b150a2d2744169a4a567592287
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446452"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="d3e35-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap メソッド</span><span class="sxs-lookup"><span data-stu-id="d3e35-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="d3e35-103">メソッドトークンとエディットコンティニュバージョン番号を指定して、シンボルリーダーメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="d3e35-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="d3e35-104">バージョン番号は1から始まり、エディットコンティニュ操作の結果としてメソッドが変更されるたびに増分されます。</span><span class="sxs-lookup"><span data-stu-id="d3e35-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3e35-105">構文</span><span class="sxs-lookup"><span data-stu-id="d3e35-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3e35-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3e35-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="d3e35-107">からメソッドメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="d3e35-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="d3e35-108">からメソッドのバージョン。</span><span class="sxs-lookup"><span data-stu-id="d3e35-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d3e35-109">入出力返された[ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3e35-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3e35-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="d3e35-110">Return Value</span></span>  
 <span data-ttu-id="d3e35-111">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d3e35-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3e35-112">要件</span><span class="sxs-lookup"><span data-stu-id="d3e35-112">Requirements</span></span>  
 <span data-ttu-id="d3e35-113">**ヘッダー:** CorSym .idl。</span><span class="sxs-lookup"><span data-stu-id="d3e35-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="d3e35-114">CorSym .h</span><span class="sxs-lookup"><span data-stu-id="d3e35-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3e35-115">参照</span><span class="sxs-lookup"><span data-stu-id="d3e35-115">See also</span></span>

- [<span data-ttu-id="d3e35-116">ISymUnmanagedReader2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3e35-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
