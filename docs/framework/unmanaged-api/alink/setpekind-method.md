---
title: SetPEKind メソッド
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179382"
---
# <a name="setpekind-method"></a><span data-ttu-id="43998-102">SetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="43998-102">SetPEKind Method</span></span>
<span data-ttu-id="43998-103">ポータブル実行可能ファイルの種類を、コンピューター固有またはマシンに依存しない型を決定します。</span><span class="sxs-lookup"><span data-stu-id="43998-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43998-104">構文</span><span class="sxs-lookup"><span data-stu-id="43998-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="43998-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="43998-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="43998-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="43998-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="43998-107">PE タイプが設定されるファイルのトークン。</span><span class="sxs-lookup"><span data-stu-id="43998-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="43998-108">非バインドネットモジュール`AssemblyID`を示さない場合は NULL にできます。</span><span class="sxs-lookup"><span data-stu-id="43998-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="43998-109">[CorPEKind 列挙](../metadata/corpekind-enumeration.md)で示されている PE の型。</span><span class="sxs-lookup"><span data-stu-id="43998-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="43998-110">NT ヘッダーに示されている、ターゲット コンピュータのアーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="43998-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43998-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="43998-111">Return Value</span></span>  
 <span data-ttu-id="43998-112">メソッドが成功した場合は、S_OKを返します。</span><span class="sxs-lookup"><span data-stu-id="43998-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43998-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="43998-113">Requirements</span></span>  
 <span data-ttu-id="43998-114">alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="43998-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43998-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="43998-115">See also</span></span>

- [<span data-ttu-id="43998-116">GetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="43998-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="43998-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43998-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="43998-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="43998-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="43998-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="43998-119">ALink API</span></span>](index.md)
