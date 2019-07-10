---
title: SetAssemblyFile2 メソッド
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d96881ce35dca1ee7a196507ef8d81a565eed82
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741506"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="4d852-102">SetAssemblyFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="4d852-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="4d852-103">名前と新しいアセンブリのオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="4d852-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="4d852-104">バインドされていないモジュールを作成する際に、このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="4d852-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d852-105">構文</span><span class="sxs-lookup"><span data-stu-id="4d852-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d852-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4d852-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="4d852-107">マニフェスト ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="4d852-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="4d852-108">[IMetaDataEmit2 インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)このファイルのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="4d852-108">[IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="4d852-109">によって表されるオプション[AssemblyFlags 列挙体](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d852-109">Options represented by [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="4d852-110">構築されるアセンブリの一意の ID を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4d852-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d852-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="4d852-111">Return Value</span></span>  
 <span data-ttu-id="4d852-112">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="4d852-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d852-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="4d852-113">Requirements</span></span>  
 <span data-ttu-id="4d852-114">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="4d852-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d852-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d852-115">See also</span></span>

- [<span data-ttu-id="4d852-116">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d852-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="4d852-117">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d852-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="4d852-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="4d852-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
