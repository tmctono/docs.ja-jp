---
title: ISymUnmanagedReader::GetMethodVersion メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5d4145e6c76cf95f2468a3f5ad59edcd310423e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160876"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="48cb0-102">ISymUnmanagedReader::GetMethodVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="48cb0-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="48cb0-103">メソッドのバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="48cb0-103">Gets the method version.</span></span> <span data-ttu-id="48cb0-104">メソッドのバージョンでは、1 から開始し、メソッドが再コンパイルされるたびに増分されます。</span><span class="sxs-lookup"><span data-stu-id="48cb0-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="48cb0-105">再コンパイルは、メソッドに変更することがなく発生します。</span><span class="sxs-lookup"><span data-stu-id="48cb0-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48cb0-106">構文</span><span class="sxs-lookup"><span data-stu-id="48cb0-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48cb0-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48cb0-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="48cb0-108">[in]バージョンを取得する方法です。</span><span class="sxs-lookup"><span data-stu-id="48cb0-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="48cb0-109">[out]メソッドのバージョンを受信する変数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="48cb0-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48cb0-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="48cb0-110">Return Value</span></span>  
 <span data-ttu-id="48cb0-111">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="48cb0-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48cb0-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="48cb0-112">Requirements</span></span>  
 <span data-ttu-id="48cb0-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="48cb0-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48cb0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="48cb0-114">See also</span></span>

- [<span data-ttu-id="48cb0-115">ISymUnmanagedReader インターフェイス</span><span class="sxs-lookup"><span data-stu-id="48cb0-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
