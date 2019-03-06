---
title: ExportNestedTypeForwarder メソッド
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ed615ea641293f8ea3fdf962e3f84d602934df60
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494689"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="49554-102">ExportNestedTypeForwarder メソッド</span><span class="sxs-lookup"><span data-stu-id="49554-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="49554-103">指定したアセンブリの型のテーブルを入れ子にされた型の型フォワーダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="49554-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49554-104">構文</span><span class="sxs-lookup"><span data-stu-id="49554-104">Syntax</span></span>  
  
```  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="49554-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="49554-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="49554-106">エクスポートするアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="49554-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="49554-107">ファイルの種類を定義するファイルのトークンまたはアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="49554-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="49554-108">型のトークンです。</span><span class="sxs-lookup"><span data-stu-id="49554-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="49554-109">親の種類のトークンです。</span><span class="sxs-lookup"><span data-stu-id="49554-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="49554-110">エクスポートする完全修飾型名。</span><span class="sxs-lookup"><span data-stu-id="49554-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="49554-111">`ComType` フラグなど`tdPublic`または`tdNested`します。</span><span class="sxs-lookup"><span data-stu-id="49554-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="49554-112">エクスポート型のトークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="49554-112">Receives token of export type.</span></span> <span data-ttu-id="49554-113">これは、入れ子にされた型の生成にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="49554-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49554-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="49554-114">Return Value</span></span>  
 <span data-ttu-id="49554-115">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="49554-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49554-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="49554-116">Requirements</span></span>  
 <span data-ttu-id="49554-117">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="49554-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49554-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="49554-118">See also</span></span>
- [<span data-ttu-id="49554-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="49554-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="49554-120">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="49554-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="49554-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="49554-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
