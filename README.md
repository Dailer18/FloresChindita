import React from 'react';
import { Button } from '@/components/ui/button';
import { motion } from 'framer-motion';
import { Rocket, BrainCircuit, BookOpen, ChevronRight } from 'lucide-react';
import { cn } from '@/lib/utils';

// Animation variants
const containerVariants = {
    hidden: { opacity: 0 },
    visible: {
        opacity: 1,
        transition: {
            delayChildren: 0.3,
            staggerChildren: 0.2,
        },
    },
};

const itemVariants = {
    hidden: { y: 20, opacity: 0 },
    visible: {
        y: 0,
        opacity: 1,
    },
};

const LandingPage = () => {
    return (
        <div className="min-h-screen bg-gradient-to-br from-gray-900 via-purple-900 to-black text-white flex flex-col">
            {/* Header Section */}
            <header className="py-6 px-4 sm:px-6 lg:px-8">
                <div className="flex justify-between items-center">
                    <h1 className="text-2xl sm:text-3xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-purple-400">
                        Learn Robotics
                    </h1>
                    {/* Removed Sign In/Sign Up.  A landing page usually doesn't have these. */}
                </div>
            </header>

            {/* Main Content Section */}
            <main className="flex-grow flex items-center justify-center px-4 sm:px-6 lg:px-8">
                <motion.div
                    className="text-center space-y-6"
                    variants={containerVariants}
                    initial="hidden"
                    animate="visible"
                >
                    <motion.h2
                        className="text-4xl sm:text-5xl lg:text-6xl font-extrabold bg-clip-text text-transparent bg-gradient-to-r from-purple-400 to-blue-400"
                        variants={itemVariants}
                    >
                        Build Your First Robot
                    </motion.h2>
                    <motion.p
                        className="text-lg sm:text-xl text-gray-300 max-w-2xl mx-auto"
                        variants={itemVariants}
                    >
                        Embark on an exciting journey into the world of robotics.  Learn the fundamentals
                        and build your own small, intelligent robots.
                    </motion.p>
                    <motion.div variants={itemVariants}>
                        <Button
                            variant="default"
                            size="lg"
                            className={cn(
                                "bg-gradient-to-r from-purple-500 to-blue-500 text-white px-8 py-3",
                                "rounded-full shadow-lg hover:shadow-xl hover:scale-105 transition-all duration-300",
                                "font-semibold text-lg flex items-center gap-2"
                            )}
                        >
                            Get Started <Rocket className="w-5 h-5" />
                        </Button>
                    </motion.div>
                </motion.div>
            </main>

            {/* Features Section (Optional, added for more content) */}
            <section className="py-16 px-4 sm:px-6 lg:px-8">
                <div className="max-w-6xl mx-auto space-y-12">
                    <h2 className="text-3xl sm:text-4xl font-semibold text-center text-gray-200">
                        Key Features and Learning
                    </h2>
                    <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                        {/* Feature 1: Hands-on Projects */}
                        <div className="bg-white/5 backdrop-blur-md rounded-xl p-6 shadow-lg border border-white/10 hover:shadow-2xl transition-all duration-300 hover:scale-[1.02]">
                            <BrainCircuit className="w-10 h-10 text-blue-400 mb-4" />
                            <h3 className="text-xl font-semibold text-white mb-2">Hands-on Projects</h3>
                            <p className="text-gray-300">
                                Build real, working robots.  From simple line followers to more complex
                                autonomous designs.
                            </p>
                            <Button variant="link" className="text-blue-400 mt-4 p-0">
                                Learn More <ChevronRight className="w-4 h-4 ml-1" />
                            </Button>
                        </div>

                        {/* Feature 2: Comprehensive Curriculum */}
                        <div className="bg-white/5 backdrop-blur-md rounded-xl p-6 shadow-lg border border-white/10 hover:shadow-2xl transition-all duration-300 hover:scale-[1.02]">
                            <BookOpen className="w-10 h-10 text-purple-400 mb-4" />
                            <h3 className="text-xl font-semibold text-white mb-2">Comprehensive Curriculum</h3>
                            <p className="text-gray-300">
                                Structured learning path covering electronics, programming, and robot
                                mechanics.
                            </p>
                            <Button variant="link" className="text-purple-400 mt-4 p-0">
                                Explore Curriculum <ChevronRight className="w-4 h-4 ml-1" />
                            </Button>
                        </div>

                        {/* Feature 3:  Beginner Friendly */}
                        <div className="bg-white/5 backdrop-blur-md rounded-xl p-6 shadow-lg border border-white/10 hover:shadow-2xl transition-all duration-300 hover:scale-[1.02]">
                            <Rocket className="w-10 h-10 text-green-400 mb-4" />
                            <h3 className="text-xl font-semibold text-white mb-2">Beginner Friendly</h3>
                            <p className="text-gray-300">
                                Designed for all skill levels, even those with no prior robotics
                                experience.
                            </p>
                            <Button variant="link" className="text-green-400 mt-4 p-0">
                                Start Learning <ChevronRight className="w-4 h-4 ml-1" />
                            </Button>
                        </div>
                    </div>
                </div>
            </section>

            {/* Footer Section */}
            <footer className="py-6 px-4 sm:px-6 lg:px-8 text-center text-gray-400">
                <p>&copy; {new Date().getFullYear()} Learn Robotics. All rights reserved.</p>
            </footer>
        </div>
    );
};

export default LandingPage;
