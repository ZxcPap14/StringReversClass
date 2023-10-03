# StringReversClass

-lib

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    
    namespace StringReverseLibrary123
    {
        public class StringReversClass
        {
            public static bool IsPalindrome(string textString)
            {
                string rev = new string(textString.ToCharArray().Reverse().ToArray());
                string z = rev.ToLower();
                string x = textString.ToLower();
                if (String.Equals(x,z))
                {
                    return true;
                }
                if (String.IsNullOrEmpty(textString))
                {
                    throw new Exception("Денчик");
                }
                return false;
            }
        }
    }
-test

    using Microsoft.VisualStudio.TestTools.UnitTesting;
    using System;
    using StringReverseLibrary123;
    using static System.Collections.Specialized.BitVector32;
    
    namespace StringReverseLibraryTests
    {
        [TestClass]
        public class StringReversTests
        {
            [TestMethod]
            public void TestMethod21()
            {
                string textString = "2002";
                bool actual = StringReversClass.IsPalindrome(textString);
                Assert.IsTrue(actual);
            }
            [TestMethod]
            public void TestMethod31()
            {
                string textString = "топот";
                bool actual = StringReversClass.IsPalindrome(textString);
                Assert.IsTrue(actual);
            }
            [TestMethod]
            public void TestMethod41()
            {
                string textString = "а роза упала на лапу азора";
                bool actual = StringReversClass.IsPalindrome(textString);
                Assert.IsTrue(actual);
            }
            [TestMethod]
            public void TestMethod1()
            {
                string textString = "айлалалай нанай";
                bool actual = StringReversClass.IsPalindrome(textString);
                Assert.IsFalse(actual);
            }
            [TestMethod]
            public void TestMet2hod1()
            {
                string textString = " ";
                Action actual = () => StringReversClass.IsPalindrome(textString);
                Assert.ThrowsException<Exception>(actual);
            }
        }
    }
