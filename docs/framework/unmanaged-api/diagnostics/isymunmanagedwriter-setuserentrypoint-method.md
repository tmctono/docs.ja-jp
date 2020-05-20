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
ms.openlocfilehash: 8b51a9dc3a968c6bd2f5f9b149f13f88dc6a1e05
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614748"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="8616e-102">ISymUnmanagedWriter::SetUserEntryPoint メソッド</span><span class="sxs-lookup"><span data-stu-id="8616e-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="8616e-103">このモジュールのエントリポイントであるユーザー定義メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="8616e-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="8616e-104">たとえば、このエントリポイントは、main の前にコンパイラで生成されたスタブではなく、ユーザーのメインメソッドである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8616e-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8616e-105">構文</span><span class="sxs-lookup"><span data-stu-id="8616e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8616e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8616e-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="8616e-107">からユーザーエントリポイントであるメソッドのメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="8616e-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8616e-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="8616e-108">Return Value</span></span>  
 <span data-ttu-id="8616e-109">メソッドが成功した場合は S_OK。それ以外の場合は、E_FAIL またはその他のエラーコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="8616e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8616e-110">要件</span><span class="sxs-lookup"><span data-stu-id="8616e-110">Requirements</span></span>  
 <span data-ttu-id="8616e-111">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="8616e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8616e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8616e-112">See also</span></span>

- [<span data-ttu-id="8616e-113">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8616e-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
