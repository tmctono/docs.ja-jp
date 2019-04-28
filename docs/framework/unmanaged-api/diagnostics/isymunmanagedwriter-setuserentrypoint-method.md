---
title: ISymUnmanagedWriter::SetUserEntryPoint メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d14d542a8c1d8adeaf56dc1564e8e10121cd4064
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650727"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="36b42-102">ISymUnmanagedWriter::SetUserEntryPoint メソッド</span><span class="sxs-lookup"><span data-stu-id="36b42-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="36b42-103">このモジュールのエントリ ポイントは、ユーザー定義のメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="36b42-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="36b42-104">たとえば、このエントリ ポイントでは、メインの前に、コンパイラによって生成されたスタブではなく、ユーザーのメイン メソッド可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36b42-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36b42-105">構文</span><span class="sxs-lookup"><span data-stu-id="36b42-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36b42-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="36b42-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="36b42-107">[in]ユーザー エントリであるメソッドのメタデータ トークンをポイントします。</span><span class="sxs-lookup"><span data-stu-id="36b42-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36b42-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="36b42-108">Return Value</span></span>  
 <span data-ttu-id="36b42-109">メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="36b42-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36b42-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="36b42-110">Requirements</span></span>  
 <span data-ttu-id="36b42-111">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="36b42-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b42-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="36b42-112">See also</span></span>

- [<span data-ttu-id="36b42-113">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36b42-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
